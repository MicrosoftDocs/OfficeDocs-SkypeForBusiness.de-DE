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
ms.openlocfilehash: ac32c4037cf275d9a6a7545701c1899742d8fd12
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705874"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Bei einer lokalen Bereitstellung von Skype for Business Server können Benutzer von Skype for Business auch Teams verwenden, aber nicht alle Teams-Funktionen stehen benutzern zur Verfügung, solange sie für die Verwendung der lokalen Skype for Business Server-Bereitstellung konfiguriert sind. Diese Benutzer werden als lokal "verwaltet" bezeichnet, und bestimmte Teams-Funktionen sind nicht verfügbar, während diese Benutzer lokal verwaltet werden, z. B.:
- Verbundanrufe und Chats über den Teams-Client des Benutzers mit Benutzern in anderen Organisationen sind nicht verfügbar.
- Interopkommunikation über den Teams-Client des Benutzers mit anderen Benutzern in der Organisation, die Skype for Business Client verwenden.
- PSTN-Anruffunktion (wenn dem Benutzer eine Telefonsystemlizenz zugewiesen ist).

Um vollständige Teams-Funktionen zu erhalten, müssen diese Benutzer von Skype for Business lokal in die Cloud verschoben werden, wodurch der Benutzer zu TeamsOnly wird. Durch das Verschieben eines Benutzers aus der lokalen Umgebung in die Cloud wird der Koexistenzmodus des Benutzers auf TeamsOnly festgelegt. Sobald Benutzer in die Cloud verschoben wurden, sind sie TeamsOnly, was bedeutet, dass alle eingehenden Chats und Anrufe in ihrem Teams-Client landen. Weitere Informationen finden Sie unter [Teams-Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence) und [Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Um Benutzer von der lokalen Skype for Business Server Bereitstellung in die Cloud zu verschieben, ist die [Konfiguration Skype for Business Hybridbereitstellung](/skypeforbusiness/hybrid/plan-hybrid-connectivity) erforderlich.  Sobald die Bereitstellung für die Hybridbereitstellung aktiviert ist, können Sie Benutzer aus der lokalen Umgebung in die Cloud verschieben, um sie wie unten beschrieben zu TeamsOnly zu machen. Bei Bedarf können Sie auch TeamsOnly-Benutzer zurück zur lokalen Skype for Bsuiness-Bereitstellung verschieben. 



## <a name="prerequisites"></a>Voraussetzungen

Voraussetzungen zum Verschieben eines Benutzers in den TeamsOnly-Modus:

- Die Organisation muss Azure AD Connect ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [Konfigurieren von Azure AD Connect](configure-azure-ad-connect.md) beschrieben.
- Skype for Business Hybrid muss konfiguriert werden, wie unter [Konfigurieren Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md) beschrieben.
- Dem Benutzer muss eine Lizenz für Teams und Skype for Business Online (Plan 2) zugewiesen werden. Auch nach der Einstellung von Skype for Business Online ist die Skype for Business Online-Lizenz weiterhin erforderlich.  Weitere Schritte:
    - Wenn der Benutzer für lokale Einwahlkonferenzen aktiviert ist, muss dem Benutzer auch eine Audiokonferenzlizenz in Teams zugewiesen sein, bevor Sie den Benutzer online verschieben. Nach der Migration zur Cloud wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt. 
    - Wenn der Benutzer für die lokale Enterprise-VoIP aktiviert ist, muss dem Benutzer eine Microsoft Teams-Telefonlizenz in Teams zugewiesen sein, bevor Sie den Benutzer online verschieben. Nach der Migration in die Cloud wird der Benutzer für das Telefonsystem in der Cloud bereitgestellt. 
  
Zum Verschieben von Benutzern zwischen einer lokalen Bereitstellung und der Cloud müssen Sie ab dem 31. Juli 2022 die folgende Mindestversion von Skype for Business Server oder Lync Server verwenden:

</br>
</br>

|Lokales Produkt|Erforderliche Mindestversion|Erforderlicher Mindestbuild|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 mit Hotfix 7|5.0.8308.1182|

</br>
</br>

## <a name="moving-users"></a>Verschieben von Benutzern

Wenn ein Benutzer aus der lokalen Umgebung in die Cloud verschoben wird:

- Der Benutzer wird zu einem TeamsOnly-Benutzer, was bedeutet, dass der Benutzer:
   -  Empfängt und initiiert alle Chats und Anrufe im Teams-Client.
   -  Plant alle Besprechungen in Teams.
   -  Chats oder Anrufe können nicht initiiert oder Besprechungen in Skype for Business geplant werden.
   -  Kann an Skype for Business Besprechungen teilnehmen, die sie in Zukunft bereits haben oder empfangen. Nachdem Microsoft jedoch die Skype for Business Online-Infrastruktur für einen bestimmten TeamsOnly-Benutzer entfernt hat, können TeamsOnly-Benutzer nur anonym an Skype for Business Besprechungen teilnehmen. Ab Oktober 2022 werden Benutzer, die nur in Hybridorganisationen von lokalen zu Teams gewechselt sind, nicht mehr mit der Skype for Business Online-Infrastruktur bereitgestellt. Wenn diese Benutzer zu einer Skype for Business Besprechung eingeladen werden, müssten sie anonym teilnehmen. Ausführliche Informationen finden Sie unter [Anleitungen für Organisationen mit lokalen Bereitstellungen von Skype for Business Server](/MicrosoftTeams/skype-for-business-online-retirement.md#guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server).

- Benutzer werden für die Interoperabilität mit Skype for Business Benutzern aktiviert und können sich auch mit anderen Organisationen verbinden.
- Kontakte aus der lokalen Umgebung werden nach Teams verschoben.
- Vorhandene Besprechungen, die sie organisiert haben, die in der Zukunft geplant sind, werden in Teams-Besprechungen konvertiert. Die Migration von Besprechungen geschieht asynchron und beginnt ungefähr 90 Minuten nach dem Verschieben des Benutzers.  Den Status der Besprechungsmigration können Sie mit [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) ermitteln. Alle Inhalte, die vor der Besprechung hochgeladen wurden, werden nicht verschoben.
- Benutzer, denen eine Microsoft Teams Phone-Lizenz zugewiesen ist, können auf PSTN-Funktionen zugreifen, sobald sie ordnungsgemäß konfiguriert sind.
 
Um Benutzer nach Teams zu verschieben, verwenden Sie entweder das cmdlet Move-CsUser oder die Skype for Business Admin Systemsteuerung, die beide lokale Tools sind. Diese Tools unterstützen die folgenden Verschiebungspfade:

- [Nur von Skype for Business Server (lokal) zu Teams](move-users-from-on-premises-to-teams.md).
- [Von online (ob nur Teams oder nicht) bis zur lokalen Bereitstellung](move-users-from-the-cloud-to-on-premises.md).


> [!NOTE] 
>  Das Verhalten für den direkten Wechsel von der lokalen Umgebung zu "Nur Teams" erfolgt automatisch, unabhängig davon, welche Version von Skype for Business Server oder Lync Server verwendet wird. Es ist nicht mehr erforderlich, den `-MoveToTeams` Wechsel `Move-CsUser` anzugeben, um Benutzer direkt von der lokalen Umgebung zu TeamsOnly zu verschieben. Wenn diese Option zuvor nicht angegeben wurde, wurden Benutzer von Skype for Business Server lokal zu Skype for Business Online umgestellt, und ihr Modus blieb unverändert. Beim Verschieben eines Benutzers aus der lokalen Umgebung in die Cloud mit `Move-CsUser`werden Benutzern automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen aus der lokalen Umgebung werden automatisch in Teams-Besprechungen konvertiert, so als ob der `-MoveToTeams` Wechsel angegeben worden wäre, unabhängig davon, ob der Wechsel tatsächlich angegeben wurde. 


## <a name="required-administrative-credentials"></a>Erforderliche administrative Anmeldeinformationen

Um Benutzer zwischen der lokalen Umgebung und der Cloud zu verschieben, müssen Sie ein Konto mit ausreichenden Berechtigungen sowohl in der lokalen Skype for Business Server-Umgebung als auch in der Teams-Organisation verwenden. Sie können entweder ein Konto verwenden, das über alle erforderlichen Berechtigungen verfügt, oder Sie können zwei Konten verwenden. Wenn Sie zwei Konten verwenden, greifen Sie mithilfe lokaler Anmeldeinformationen auf die lokalen Tools zu, und in diesen Tools würden Sie zusätzliche Anmeldeinformationen für ein Teams-Administratorkonto angeben.  

- In der lokalen Umgebung muss der Benutzer, der die Verschiebung ausführt, über die Rollen CSServerAdministrator, CsUserAdministrator und RTCUniversalUserAdmins in Skype for Business Server verfügen.
- In Teams muss der Benutzer, der die Verschiebung ausführt, Mitglied mindestens einer der folgenden Rollen sein:
  - Rolle "Globaler Administrator"
  - Teams-Administratorrolle
  - Skype for Business Administratorrolle.  

    > [!Important]
    > - Wenn Sie die Skype for Business Admin Systemsteuerung verwenden, werden Sie wie oben erwähnt aufgefordert, Anmeldeinformationen für ein Microsoft 365-Konto mit den entsprechenden Rollen anzugeben. Sie müssen ein Konto angeben, das auf .onmicrosoft.com endet. Wenn dies nicht möglich ist, verwenden Sie das cmdlet Move-CsUser.
    >- Wenn Sie Move-CsUser in PowerShell verwenden, können Sie entweder ein Konto verwenden, das auf .onmicrosoft.com endet, oder Sie können jedes lokale Konto verwenden, das mit Azure AD synchronisiert wird, vorausgesetzt, Sie geben auch den Parameter HostedMigrationOverrideUrl im Cmdlet an. Der Wert der URL zur Außerkraftsetzung der gehosteten Migration ist eine Variante der folgenden URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Ersetzen Sie in der obigen URL den XX-Wert durch zwei oder drei Zeichen, die wie folgt bestimmt werden:
    >   - Führen Sie in einer Teams PowerShell-Sitzung das folgende Cmdlet aus:<br>`Get-CsTenant | ft ServiceInstance`
    >   - Der resultierende Wert weist das folgende Format auf:<br>`MicrosoftCommunicationsOnline/YYYY-XX-ZZ`
    >   - Der zwei- oder dreistellige Code ist der IM Abschnitt YYYY-XX-ZZ enthaltene XX. Wenn es sich um einen zweistelligen Code handelt, handelt es sich um eine Ziffer gefolgt von einer Zahl (z. B. 4A). Wenn es sich um einen dreistelligen Code handelt, werden zwei Buchstaben gefolgt von einer Ziffer (z. B. JP1) verwendet. Ein Beispiel ist NOAM-4A-S7.


## <a name="voice-configuration-requirements"></a>Anforderungen an die Sprachkonfiguration

Wenn Benutzer lokal für Enterprise-VoIP konfiguriert sind, müssen Sie die Aktualisierung ihrer VoIP-Konfiguration koordinieren, wenn Sie sie in die Online-Umgebung verschieben. Alternativ können Sie sie auch ohne Telefoniefunktionen migrieren. 
- Sie können den Telefonieanbieter eines Benutzers aktualisieren, um einen [Microsoft-Anrufplan](/microsoftteams/calling-plans-for-office-365) zu verwenden. Dies ist eine Option, ob Benutzer Teams oder Skype for Business Clients verwenden.
- Sie können weiterhin Ihren lokalen PSTN-Anbieter verwenden:
  - VoIP-Benutzer, die Teams verwenden, müssen für [Direct Routing](/microsoftteams/direct-routing-plan) konfiguriert sein. Direct Routing ist nur verfügbar, nachdem der Benutzer von der lokalen Umgebung in die Online-Umgebung verschoben wurde.

Weitere Informationen zu Telefonieoptionen in Hybridumgebungen, einschließlich einer Unterstützungsmatrix, finden Sie [unter Benutzerkonten in einer Hybridumgebung mit PSTN-Konnektivität](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Andere Überlegungen

Die Richtlinien (z. B. die Kontrolle von Nachrichten, Besprechungen und Anrufverhalten) in lokalen und Online-Umgebungen sind unabhängig voneinander. Möglicherweise sollten Sie erwägen, Richtlinien in der Umgebung zu konfigurieren und sie dem Benutzer zuzuweisen, bevor Sie diesen Benutzer von der lokalen Bereitstellung in die Cloud verschieben, damit er die richtige Konfiguration hat, sobald er zu online migriert wird.

## <a name="see-also"></a>Siehe auch

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Einrichten von Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planen von direktem Routing](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
