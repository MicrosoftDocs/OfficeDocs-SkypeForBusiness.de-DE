---
title: Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Zusammenfassung: In einer lokalen Bereitstellung von Skype for Business Server, die für die Hybridbereitstellung aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud verschieben.'
ms.openlocfilehash: 15e237fdf54854a86216bc3890ae26209449c146
ms.sourcegitcommit: d847256fca80e4e8954f767863c880dc8472ca04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2022
ms.locfileid: "65304003"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In einer lokalen Bereitstellung von Skype for Business Server, die für die Hybridbereitstellung aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und Teams verschieben. Ob ein Benutzer lokal oder in der Cloud verwaltet wird, gibt das Skype for Business Home des Benutzer an:

- Benutzer, die lokal verwaltet werden, interagieren mit lokalen Skype for Business Servern.
- Benutzer, die online verwaltet werden, können mit dem Teams-Dienst interagieren.

*Teams Benutzer verfügen grundsätzlich über ein Skype for Business Zuhause, unabhängig davon, ob sie Skype for Business verwenden oder nicht.* Wenn Sie über lokale Skype for Business Benutzer verfügen, die auch Teams (nebeneinander) verwenden, werden diese Benutzer lokal verwaltet. Teams Benutzer mit lokalen Skype for Business können weder mit Skype for Business Benutzern von ihrem Teams-Client aus zusammenarbeiten noch von Teams mit Benutzern in einer Verbundorganisation kommunizieren. Diese Funktionalität ist erst vollständig verfügbar, nachdem der Benutzer von Skype for Business lokal auf Online umgestellt und teamsonly erstellt wurde. Es wird empfohlen, Ihre Benutzer in den TeamsOnly-Modus zu verschieben, wodurch sichergestellt wird, dass das Routing aller eingehenden Chats und Anrufe in ihrem Teams-Client erfolgt. Weitere Informationen finden Sie [unter Teams Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence) und [Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Voraussetzungen

Voraussetzungen zum Verschieben eines Benutzers in den TeamsOnly-Modus:

- Die Organisation muss Azure AD Verbinden ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [Konfigurieren von Azure AD Verbinden](configure-azure-ad-connect.md) beschrieben.
- Skype for Business Hybrid muss konfiguriert werden, wie unter [Konfigurieren Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md) beschrieben.
- Dem Benutzer muss eine Lizenz für Teams und Skype for Business Online (Plan 2) zugewiesen werden. Auch nach der Einstellung von Skype for Business Online ist die Skype for Business Online-Lizenz weiterhin erforderlich.  Weitere Schritte:
    - Wenn der Benutzer lokal für Einwahlkonferenzen aktiviert ist, muss dem Benutzer auch eine Audiokonferenz Lizenz in Teams zugewiesen sein, bevor Sie den Benutzer online verschieben. Nach der Migration zur Cloud wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt. 
    - Wenn der Benutzer für die lokale Enterprise-VoIP aktiviert ist, muss dem Benutzer eine Telefonsystem Lizenz in Teams zugewiesen sein, bevor Sie den Benutzer online verschieben. Nach der Migration in die Cloud wird der Benutzer für Telefonsystem in der Cloud bereitgestellt. 


## <a name="moving-users"></a>Verschieben von Benutzern

Wenn ein Benutzer aus der lokalen Umgebung in die Cloud verschoben wird:

- Teams Benutzer werden für die Interoperabilität mit Skype for Business Benutzern aktiviert, und wenn sie TeamsOnly sind, können sie sich auch mit anderen Organisationen verbinden.

- Kontakte aus der lokalen Umgebung werden in Teams verschoben.

- Vorhandene Besprechungen, die sie organisiert haben, die in der Zukunft geplant sind, werden in Teams Besprechungen konvertiert. Die Migration von Besprechungen geschieht asynchron und beginnt ungefähr 90 Minuten nach dem Verschieben des Benutzers.  Den Status der Besprechungsmigration können Sie mit [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) ermitteln. Alle Inhalte, die vor der Besprechung hochgeladen wurden, werden nicht verschoben.

Um Benutzer in Teams zu verschieben, verwenden Sie entweder das cmdlet Move-CsUser oder die Skype for Business Admin Systemsteuerung, die beide lokale Tools sind. Diese Tools unterstützen die folgenden Verschiebungspfade:

- [Von Skype for Business Server (lokal) direkt zu Teams Only](move-users-from-on-premises-to-teams.md).  Das Verhalten, direkt von der lokalen Zu Teams Nur zu wechseln, ist jetzt automatisch, unabhängig davon, welche Version von Skype for Business Server oder Lync Server verwendet wird. Es ist nicht mehr erforderlich, den `-MoveToTeams` Schalter anzugeben, um dieses Verhalten abzurufen.  
- [Von online (ob Teams Nur oder nicht), um lokal](move-users-from-the-cloud-to-on-premises.md).

> [!NOTE] 
> Es ist nicht mehr erforderlich, den Schalter "-MoveToTeams" in Move-CsUser anzugeben, um Benutzer direkt von der lokalen Umgebung zu TeamsOnly zu verschieben. Wenn diese Option zuvor nicht angegeben wurde, wurden Benutzer von Skype for Business Server lokal zu Skype for Business Online umgestellt, und ihr Modus blieb unverändert. Beim Verschieben eines Benutzers aus der lokalen Umgebung in die Cloud mit Move-CsUser werden Benutzern nun automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen aus der lokalen Umgebung werden automatisch in Teams Besprechungen konvertiert, so als ob die `-MoveToTeams` Option angegeben worden wäre, unabhängig davon, ob die Option tatsächlich angegeben wurde. 
> 

## <a name="required-administrative-credentials"></a>Erforderliche administrative Anmeldeinformationen

Um Benutzer zwischen der lokalen Umgebung und der Cloud zu verschieben, müssen Sie ein Konto mit ausreichenden Berechtigungen sowohl in der lokalen Skype for Business Server-Umgebung als auch in der Teams Organisation verwenden. Sie können entweder ein Konto verwenden, das über alle erforderlichen Berechtigungen verfügt, oder Sie können zwei Konten verwenden. Wenn Sie zwei Konten verwenden, greifen Sie mithilfe lokaler Anmeldeinformationen auf die lokalen Tools zu, und in diesen Tools würden Sie zusätzliche Anmeldeinformationen für ein Teams Administratorkonto angeben.  

- In der lokalen Umgebung muss der Benutzer, der die Verschiebung ausführt, über die Rollen CSServerAdministrator, CsUserAdministrator und RTCUniversalUserAdmins in Skype for Business Server verfügen.
- In Teams muss der Benutzer, der die Verschiebung ausführt, Mitglied mindestens einer der folgenden Rollen sein:
  - Rolle "Globaler Administrator"
  - Teams Administratorrolle
  - Skype for Business Administratorrolle.  

    > [!Important]
    > - Wenn Sie die Skype for Business Admin Systemsteuerung verwenden, werden Sie aufgefordert, Anmeldeinformationen für ein Microsoft 365 Konto mit den entsprechenden Rollen anzugeben, wie oben erwähnt. Sie müssen ein Konto angeben, das auf .onmicrosoft.com endet. Wenn dies nicht möglich ist, verwenden Sie das cmdlet Move-CsUser.
    >- Wenn Sie Move-CsUser in PowerShell verwenden, können Sie entweder ein Konto verwenden, das auf .onmicrosoft.com endet, oder Sie können jedes lokale Konto verwenden, das mit Azure AD synchronisiert wird, vorausgesetzt, Sie geben auch den Parameter HostedMigrationOverrideUrl im Cmdlet an. Der Wert der URL zur Außerkraftsetzung der gehosteten Migration ist eine Variante der folgenden URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Ersetzen Sie in der obigen URL den XX-Wert durch zwei oder drei Zeichen, die wie folgt bestimmt werden:
    >   - Führen Sie in einer Teams PowerShell-Sitzung das folgende Cmdlet aus:<br>`Get-CsTenant | ft ServiceInstance`
    >   - Der resultierende Wert weist das folgende Format auf:<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - Der zwei- oder dreistellige Code ist der IM Abschnitt YYYY-XX-ZZ enthaltene XX. Wenn es sich um einen zweistelligen Code handelt, handelt es sich um eine Ziffer gefolgt von einer Zahl (z. B. 4A). Wenn es sich um einen dreistelligen Code handelt, werden zwei Buchstaben gefolgt von einer Ziffer (z. B. JP1) verwendet. Ein Beispiel ist NOAM-4A-S7.


## <a name="voice-configuration-requirements"></a>VoIP-Konfigurationsanforderungen

Wenn Benutzer lokal für Enterprise-VoIP konfiguriert sind, müssen Sie die Aktualisierung ihrer VoIP-Konfiguration koordinieren, wenn Sie sie in die Online-Umgebung verschieben. Alternativ können Sie sie auch ohne Telefoniefunktionen migrieren. Die verfügbaren Optionen hängen davon ab, ob der Benutzer die Teams oder Skype for Business Client verwendet, sobald er online ist:

- Sie können den Telefonieanbieter eines Benutzers aktualisieren, um einen [Microsoft-Anrufplan](/microsoftteams/calling-plans-for-office-365) zu verwenden. Dies ist eine Option, ob Benutzer Teams oder Skype for Business Clients verwenden.
- Sie können weiterhin Ihren lokalen PSTN-Anbieter verwenden:
  - VoIP-Benutzer, die Teams verwenden, müssen für [Direct Routing](/microsoftteams/direct-routing-plan) konfiguriert sein. Direct Routing ist nur verfügbar, nachdem der Benutzer von der lokalen Umgebung in die Online-Umgebung verschoben wurde.
  - VoIP-Benutzer, die den Skype for Business-Client verwenden, nachdem sie online verschoben wurden, müssen für Skype for Business Hybrid Voice-Funktionen konfiguriert werden.

Weitere Informationen zu Telefonieoptionen in Hybridumgebungen, einschließlich einer Unterstützungsmatrix, finden Sie [unter Benutzerkonten in einer Hybridumgebung mit PSTN-Konnektivität](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Andere Überlegungen

Die Richtlinien (z. B. die Kontrolle von Nachrichten, Besprechungen und Anrufverhalten) in lokalen und Online-Umgebungen sind unabhängig voneinander. Möglicherweise sollten Sie erwägen, Richtlinien in der Umgebung zu konfigurieren und sie dem Benutzer zuzuweisen, bevor Sie diesen Benutzer von der lokalen Bereitstellung in die Cloud verschieben, damit er die richtige Konfiguration hat, sobald er zu online migriert wird.

## <a name="see-also"></a>Siehe auch

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Einrichten von Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planen von direktem Routing](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
