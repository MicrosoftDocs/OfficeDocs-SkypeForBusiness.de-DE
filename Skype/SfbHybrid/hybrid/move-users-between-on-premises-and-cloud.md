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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Zusammenfassung: In einer lokalen Bereitstellung von Skype for Business Server, die für die Hybridbereitstellung aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud verschieben (ob zu Microsoft Teams oder zu Skype for Business Online).'
ms.openlocfilehash: b4b354a6a43ab58740a053f86d9b7da1faaeb0da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110671"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud

Bei einer lokalen Bereitstellung von Skype for Business Server, die für Hybridnutzung aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud verschieben (entweder in Microsoft Teams oder in Skype for Business Online). Ob ein Benutzer lokal oder in der Cloud verwaltet wird, gibt das Skype for Business Home des Benutzer an:

- Lokale Benutzer interagieren mit lokalen Skype for Business-Servern.
- Online verwaltete Benutzer können mit Skype for Business-Onlinediensten interagieren.

*Teams-Benutzer verfügen grundsätzlich über ein Skype for Business-Heim, unabhängig davon, ob sie Skype for Business verwenden oder nicht.* Wenn Sie über lokale Skype for Business-Benutzer verfügen, die auch Teams (nebeneinander) verwenden, werden diese Benutzer lokal heimgeheimst. Teams-Benutzer mit lokalen Skype for Business-Benutzern können weder über ihren Teams-Client mit Skype for Business-Benutzern zusammenarbeiten, noch können sie von Teams aus mit Benutzern in einer Verbundorganisation kommunizieren. Diese Funktionalität ist nur verfügbar, nachdem der Benutzer von Skype for Business lokal in online verschoben wurde. Wenn Sie einen Benutzer auf "Online" umstellen, können Sie ihm entweder die Verwendung von Skype for Business Online (und optional Teams) gestatten, oder Sie können ihm den TeamsOnly-Modus zuweisen. Wenn Ihre Organisation bereits Teams verwendet, wird dringend empfohlen, die Benutzer in den Teams Only-Modus zu verschieben. Dadurch wird sichergestellt, dass alle eingehenden Chats und Anrufe an ihren Team-Client weitergeleitet werden. Weitere Informationen finden Sie unter Richtlinien zur Koexistenz von Teams mit [Skype for Business](/microsoftteams/coexistence-chat-calls-presence) und Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business [verwenden.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="prerequisites"></a>Voraussetzungen

Voraussetzungen für das Verschieben eines Benutzers in die Cloud (ob in den Modus "Nur Skype for Business" oder "Teams Only"):

- Die Organisation muss Azure AD Connect ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [Configure Azure AD Connect beschrieben.](configure-azure-ad-connect.md)
- Skype for Business hybrid muss konfiguriert werden, wie unter [Configure Skype for Business hybrid beschrieben.](configure-federation-with-skype-for-business-online.md)
- Der Benutzer muss über eine Lizenz für Skype for Business Online (Plan 2) sowie, bei Verwendung von Teams, zudem über eine Teams-Lizenz verfügen.  Weitere Schritte:
    - Wenn der Benutzer für Einwahlkonferenzen lokal aktiviert ist, muss dem Benutzer standardmäßig auch eine Lizenz für Audiokonferenzen in Microsoft 365 oder Office 365 zugewiesen sein, bevor Sie den Benutzer online verschieben. Nach der Migration zur Cloud wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt. Wenn Sie einen Benutzer aus einem bestimmten Grund in die Cloud verschieben möchten, aber keine Audiokonferenzfunktionen verwenden möchten, können Sie diese Überprüfung überschreiben, indem Sie den `BypassAudioConferencingCheck` Parameter in `Move-CsUser` angeben.
    - Wenn der Benutzer für Enterprise-VoIP lokal aktiviert ist, muss dem Benutzer standardmäßig eine Telefonsystemlizenz in Microsoft 365 oder Office 365 zugewiesen sein, bevor Sie den Benutzer online verschieben. Nach der Migration zur Cloud wird der Benutzer für das Telefonsystem in der Cloud bereitgestellt. Wenn Sie einen Benutzer aus einem bestimmten Grund in die Cloud verschieben möchten, aber keine Telefonsystemfunktionalität verwenden möchten, können Sie diese Überprüfung überschreiben, indem Sie den `BypassEnterpriseVoiceCheck` Parameter in `Move-CsUser` angeben.


## <a name="moving-users"></a>Verschieben von Benutzern

Wenn ein Benutzer aus der lokalen Umgebung in die Cloud verschoben wird:

- Der Benutzer beginnt für alle Skype for Business-Funktionen mit der Verwendung der Skype for Business Online-Dienste in der Cloud.
- Teams-Benutzer werden zur Interoperabilität mit Skype for Business-Benutzern aktiviert und können auch einen Verbund mit anderen Organisationen bilden.
- Kontakte von lokalen Stellen werden in die Cloud verschoben (entweder Skype for Business oder Teams).
- Vorhandene Besprechungen, die sie in Zukunft organisiert haben, werden zu Online migriert: Wenn Benutzer direkt zu TeamsOnly verschoben werden (siehe unten), werden Besprechungen in Teams-Besprechungen konvertiert, andernfalls bleiben Besprechungen Skype for Business, werden aber migriert, sodass sie online statt lokal gehostet werden.  Die Migration von Besprechungen geschieht asynchron und beginnt ungefähr 90 Minuten nach dem Verschieben des Benutzers.  Den Status der Besprechungsmigration können Sie mit [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) ermitteln. Bitte beachten Sie: Alle Inhalte, die im Vorfeld der Besprechung hochgeladen wurden, werden nicht verschoben.

Verwenden Sie entweder das cmdlet Move-CsUser oder die Skype for Business Admin Systemsteuerung, die beide lokale Tools sind, um Benutzer zwischen lokal und der Cloud zu verschieben (zu Teams oder zu Skype for Business Online). Diese Tools unterstützen drei unterschiedliche Pfade für die Migration:

- [Von Skype for Business Server (lokal) zu Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Von Skype for Business Server (lokal) direkt](move-users-from-on-premises-to-teams.md) zu Teams Only (wodurch sie auch zu Skype for Business Online verlagert werden).  Die Option, direkt von lokal zu Teams Only zu wechseln, ist in Skype for Business Server 2019 und kumulativem Update 8 für Skype for Business Server 2015 verfügbar. Organisationen, die frühere Versionen von Skype for Business Server verwenden, können Benutzer in den TeamsOnly-Modus verschieben, indem sie sie zuerst zu Skype for Business Online migrieren und diesen Benutzern dann den TeamsOnly-Modus zuweisen, sobald sie online sind.
- [Von online (ob nur Teams oder nicht) zu lokal](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Erforderliche administrative Anmeldeinformationen

Um Benutzer zwischen lokalen und cloudbasierten Umgebungen zu verschieben, müssen Sie ein Konto mit ausreichenden Berechtigungen sowohl in der lokalen Skype for Business Server-Umgebung als auch in der Microsoft 365- oder Office 365-Organisation verwenden. Sie können entweder ein Konto verwenden, das über alle erforderlichen Berechtigungen verfügt, oder Sie können zwei Konten verwenden, in diesem Fall würden Sie mit lokalen Anmeldeinformationen auf die lokalen Tools zugreifen, und dann würden Sie in diesen Tools zusätzliche Anmeldeinformationen für ein Microsoft 365- oder Office 365-Administratorkonto angeben.  

- In der lokalen Umgebung muss der Benutzer, der die Migration ausführt, über die Rolle CSServerAdminstrator in Skype for Business Server verfügen.
- In Microsoft 365 und Office 365 muss der Benutzer, der die Bewegung vor sich hat, entweder ein globaler Administrator sein oder sowohl über Skype for Business-Administrator- als auch über Benutzeradministratorrollen verfügen.  

    > [!Important]
    > - Wenn Sie die Skype for Business-Admin-Systemsteuerung verwenden, werden Sie aufgefordert, Anmeldeinformationen für ein Microsoft 365- oder Office 365-Konto mit den entsprechenden Rollen zur Verfügung zu stellen, wie oben erwähnt. Sie müssen ein Konto, das in ".onmicrosoft.com" endet, onmicrosoft.com. Wenn dies nicht möglich ist, verwenden Sie das cmdlet Move-CsUser Cmdlet.
    >- Wenn Sie Move-CsUser in PowerShell verwenden, können Sie entweder ein Konto verwenden, das in .onmicrosoft.com endet, oder Sie können ein lokales Konto verwenden, das mit Azure AD synchronisiert wird, vorausgesetzt, Sie geben auch den Parameter HostedMigrationOverrideUrl im Cmdlet an. Der Wert der gehosteten Migrationsüberschreibungs-URL ist eine Variante der folgenden URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Ersetzen Sie in der obigen URL xx durch zwei oder drei Zeichen, die wie folgt bestimmt werden:
    >   - Führen Sie in einer Skype for Business Online PowerShell-Sitzung das folgende Cmdlet aus:<br>`Get-CsTenant|ft identity`
    >    - Der resultierende Wert hat das folgende Format:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Der zwei- oder dreistellige Code ist der xx im Abschnitt DC=lyncXX001. Wenn es sich um einen zweistelligen Code ist, ist es eine Ziffer gefolgt von einer Zahl (z. B. 0a). Wenn es sich um einen dreistelligen Code geht, werden zwei Buchstaben gefolgt von einer Ziffer (z. B. jp1) angezeigt. In allen Fällen wird 001 unmittelbar nach dem XX-Code angezeigt.


## <a name="voice-configuration-requirements"></a>Anforderungen an die Sprachkonfiguration

Wenn Benutzer für unternehmensweites Voice in lokal konfiguriert sind, müssen Sie die Aktualisierung ihrer Sprachkonfiguration koordinieren, wenn Sie sie ins Internet verschieben, oder Alternativ können Sie sie ohne Telefoniefunktionen migrieren. Die verfügbaren Optionen hängen davon ab, ob der Benutzer den Teams- oder Skype for Business-Client verwendet, sobald er online ist:

- Sie können den Telefonieanbieter eines Benutzers so aktualisieren, dass er einen [Microsoft-Anrufplan verwendet.](/microsoftteams/calling-plans-for-office-365) Dies ist eine Option, ob Benutzer Teams- oder Skype for Business-Clients verwenden.
- Sie können weiterhin Ihren lokalen PSTN-Anbieter verwenden:
  - Sprachbenutzer, die Teams verwenden, müssen für direktes [Routing konfiguriert werden.](/microsoftteams/direct-routing-plan) Direktes Routing ist nur verfügbar, nachdem der Benutzer von lokal in online verschoben wurde.
  - Sprachbenutzer, die den Skype for Business-Client verwenden, nachdem sie online verschoben wurden, müssen für die Skype for Business Hybrid Voice-Funktionalität konfiguriert sein.

Weitere Informationen zu Telefonieoptionen in Hybridumgebungen sowie eine Unterstützungsmatrix finden Sie unter Benutzerkonten in einer Hybridumgebung [mit PSTN-Konnektivität.](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)

## <a name="other-considerations"></a>Andere Überlegungen

Die Richtlinien (z. B. die Kontrolle von Nachrichten, Besprechungen und Anrufverhalten) in lokalen und Online-Umgebungen sind unabhängig voneinander. Sie sollten erwägen, alle Richtlinien in der Umgebung zu konfigurieren und sie dem Benutzer zuzuordnen, bevor Sie diesen Benutzer von der lokalen in die Cloud verschieben, damit er die richtige Konfiguration hat, sobald er zu online migriert wird.

## <a name="see-also"></a>Siehe auch

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Einrichten von Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planen von direktem Routing](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)