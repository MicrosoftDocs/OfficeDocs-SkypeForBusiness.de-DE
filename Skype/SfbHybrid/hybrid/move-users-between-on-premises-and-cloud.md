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
description: 'Zusammenfassung: In einer lokalen Bereitstellung von Skype for Business Server, die für die Hybridbereitstellung aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud verschieben (unabhängig davon, ob Sie Microsoft Teams oder Skype for Business Online vor derEntbundezeit verwenden)..'
ms.openlocfilehash: 8fce1799ba3e10f2e96b8beab0fbde7805c7c229
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305957"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud

In einer lokalen Bereitstellung von Skype for Business Server, die für die Hybridbereitstellung aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud verschieben (unabhängig davon, ob sie Microsoft Teams oder Skype for Business Online vor dem Aus ist). Ob ein Benutzer lokal oder in der Cloud verwaltet wird, gibt das Skype for Business Home des Benutzers an:

- Lokale Benutzer interagieren mit lokalen Skype for Business Server.
- Online verwaltete Benutzer können mit Skype for Business-Onlinediensten interagieren.

*Teams Benutzer haben inhärent ein Skype for Business, unabhängig davon, ob sie Skype for Business verwenden.* Wenn Sie über lokale Benutzer Skype for Business, die auch Teams verwenden, werden diese Benutzer lokal heimgeheimt. Teams Benutzer mit Skype for Business lokalen Benutzern haben nicht die Möglichkeit, mit Skype for Business-Benutzern über ihren Teams-Client zu kommunizieren, noch können sie von Teams mit Benutzern in einer Verbundorganisation kommunizieren. Diese Funktionalität ist nur dann vollständig verfügbar, wenn der Benutzer von einer lokalen Skype for Business in online verschoben und TeamsOnly gemacht wurde. Wenn Sie einen Benutzer auf "Online" umstellen, können Sie ihm entweder die Verwendung von Skype for Business Online (und optional Teams) gestatten, oder Sie können ihm den TeamsOnly-Modus zuweisen. Es wird dringend empfohlen, dass Sie Ihre Benutzer in den Teams-Modus verschieben, um sicherzustellen, dass das Routing aller eingehenden Chats und Anrufe in ihrem Teams wird. Weitere Informationen finden Sie unter [Teams Koexistenz](/microsoftteams/coexistence-chat-calls-presence) mit Skype for Business und [Migrations-](/microsoftteams/migration-interop-guidance-for-teams-with-skype)und Interoperabilitätsanleitungen für Organisationen, die Teams zusammen mit Skype for Business.

## <a name="prerequisites"></a>Voraussetzungen

Voraussetzungen für das Verschieben eines Benutzers in die Cloud (ob Teams Nur-Modus oder Skype for Business Online vor der Rente):

- Die Organisation muss azure AD Verbinden ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [Configure Azure AD Verbinden beschrieben.](configure-azure-ad-connect.md)
- Skype for Business Hybrid muss konfiguriert werden, wie unter [Configure Skype for Business hybrid beschrieben.](configure-federation-with-skype-for-business-online.md)
- Dem Benutzer muss eine Lizenz für Teams und Skype for Business Online (Plan 2) zugewiesen werden. Auch nach dem Ausscheiden Skype for Business Online ist Skype for Business Online-Läuse weiterhin erforderlich.  Weitere Schritte:
    - Wenn der Benutzer für Einwahlkonferenzen lokal aktiviert ist, muss dem Benutzer standardmäßig auch eine Audiokonferenzlizenz in Teams zugewiesen sein, bevor Sie den Benutzer online verschieben. Nach der Migration zur Cloud wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt. Wenn Sie einen Benutzer aus einem bestimmten Grund in die Cloud verschieben möchten, aber keine Audiokonferenzfunktionen verwenden möchten, können Sie diese Überprüfung überschreiben, indem Sie den `BypassAudioConferencingCheck` Parameter in `Move-CsUser` angeben.
    - Wenn der Benutzer für die Enterprise-VoIP lokal aktiviert ist, muss dem Benutzer standardmäßig eine Telefonsystem-Lizenz in Teams zugewiesen sein, bevor Sie den Benutzer online verschieben. Nach der Migration zur Cloud wird der Benutzer für das Telefonsystem in der Cloud bereitgestellt. Wenn Sie einen Benutzer aus einem bestimmten Grund in die Cloud verschieben möchten, aber keine Telefonsystem verwenden, können Sie diese Überprüfung überschreiben, indem Sie den `BypassEnterpriseVoiceCheck` Parameter in `Move-CsUser` angeben.


## <a name="moving-users"></a>Verschieben von Benutzern

Wenn ein Benutzer aus der lokalen Umgebung in die Cloud verschoben wird:

- Teams Benutzer werden für die Interoperabilität mit Skype for Business aktiviert, und wenn es sich um TeamsOnly handelt, können sie auch mit anderen Organisationen zusammenarbeiten.
- Der Benutzer beginnt für alle Skype for Business-Funktionen mit der Verwendung der Skype for Business Online-Dienste in der Cloud.
- Kontakte von lokalen Stellen werden in die Cloud verschoben (entweder in Teams oder Skype for Business Online).
- Vorhandene Besprechungen, die sie organisiert haben, die in Zukunft geplant sind, werden zu Online migriert: Wenn Benutzer direkt zu TeamsOnly verschoben werden (siehe unten), werden Besprechungen in Teams-Besprechungen konvertiert, andernfalls bleiben Besprechungen Skype for Business, werden jedoch migriert, sodass sie online statt lokal gehostet werden.  Die Migration von Besprechungen geschieht asynchron und beginnt ungefähr 90 Minuten nach dem Verschieben des Benutzers.  Den Status der Besprechungsmigration können Sie mit [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) ermitteln. Bitte beachten Sie: Alle Inhalte, die im Vorfeld der Besprechung hochgeladen wurden, werden nicht verschoben.

Verwenden Sie entweder das cmdlet Move-CsUser oder die Skype for Business-Admin-Systemsteuerung, die beide lokale Tools sind, um Benutzer zwischen der lokalen und der Cloud zu verschieben (ob Teams oder Skype for Business Online). Diese Tools unterstützen drei unterschiedliche Pfade für die Migration:

- [Von Skype for Business Server (lokal) direkt](move-users-from-on-premises-to-teams.md) zu Teams Only (wodurch sie auch zu Skype for Business Online) werden.  Die Option, direkt von lokal zu Teams  Nur zu wechseln, ist derzeit in Skype for Business Server 2019 sowie kumulatives Update 8 für Skype for Business Server 2015 verfügbar. Organisationen, die frühere Versionen von Skype for Business Server verwenden, können Benutzer in den TeamsOnly-Modus verschieben, indem sie sie zuerst zu Skype for Business Online migrieren und diesen Benutzern dann den TeamsOnly-Modus zuweisen, sobald sie online sind. 

> [!NOTE] 
> Es wird bald nicht mehr erforderlich sein, den Switch -MoveToTeams in Move-CsUser, um Benutzer direkt von lokalen zu TeamsOnly zu verschieben. Wenn diese Option derzeit nicht angegeben ist, wechseln Benutzer von der lokalen Skype for Business Server zu Skype for Business Online, und ihr Modus bleibt unverändert. Nach der Rente wird Benutzern beim Verschieben eines Benutzers von der lokalen in die Cloud mit Move-CsUser automatisch der TeamsOnly-Modus zugewiesen, und ihre Besprechungen von lokalen Besprechungen werden automatisch in Teams-Besprechungen konvertiert, so als ob die Option -MoveToTeams angegeben worden wäre, unabhängig davon, ob die Option tatsächlich angegeben wurde. Wir gehen davon aus, dass diese Funktionalität vor dem tatsächlichen Ausstand vom 31. Juli 2021 veröffentlicht wird.

- [Von Skype for Business Server (lokal) zu Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md). Diese Option ist bald nicht mehr verfügbar.
- [Von online (ob Teams oder nicht) zu lokal](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Erforderliche administrative Anmeldeinformationen

Um Benutzer zwischen lokalen und cloudbasierten Umgebungen zu verschieben, müssen Sie ein Konto mit ausreichenden Berechtigungen sowohl in der lokalen Skype for Business Server-Umgebung als auch in der Teams verwenden. Sie können entweder ein Konto verwenden, das über alle erforderlichen Berechtigungen verfügt, oder Sie können zwei Konten verwenden, in diesem Fall würden Sie mit lokalen Anmeldeinformationen auf die lokalen Tools zugreifen, und dann würden Sie in diesen Tools zusätzliche Anmeldeinformationen für ein Teams-Administratorkonto angeben.  

- In der lokalen Umgebung muss der Benutzer, der die Migration ausführt, über die Rolle CSServerAdminstrator in Skype for Business Server verfügen.
- In Teams muss der Benutzer, der die Bewegung vor sich hat, eines der folgenden Kriterien erfüllen:
  - Der Benutzer ist Mitglied der Rolle "Globaler Administrator".
  - Der Benutzer ist Mitglied der Rollen Teams administrator und user adminstrator.
  - Der Benutzer ist Mitglied der Rollen Skype for Business Administrator und Benutzeradministrator.  

    > [!Important]
    > - Wenn Sie die Skype for Business Admin Control Panel verwenden, werden Sie aufgefordert, Anmeldeinformationen für ein Microsoft 365-Konto mit den entsprechenden Rollen zur Verfügung zu stellen, wie oben erwähnt. Sie müssen ein Konto, das in ".onmicrosoft.com" endet, onmicrosoft.com. Wenn dies nicht möglich ist, verwenden Sie das cmdlet Move-CsUser Cmdlet.
    >- Wenn Sie Move-CsUser in PowerShell verwenden, können Sie entweder ein Konto verwenden, das in .onmicrosoft.com endet, oder Sie können ein lokales Konto verwenden, das mit Azure AD synchronisiert wird, vorausgesetzt, Sie geben auch den Parameter HostedMigrationOverrideUrl im Cmdlet an. Der Wert der gehosteten Migrationsüberschreibungs-URL ist eine Variante der folgenden URL: https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Ersetzen Sie in der obigen URL xx durch zwei oder drei Zeichen, die wie folgt bestimmt werden:
    >   - Führen Sie Teams powerShell-Sitzung das folgende Cmdlet aus:<br>`Get-CsTenant|ft identity`
    >   - Der resultierende Wert hat das folgende Format:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >   - Der zwei- oder dreistellige Code ist der xx im Abschnitt DC=lyncXX001. Wenn es sich um einen zweistelligen Code ist, ist es eine Ziffer gefolgt von einer Zahl (z. B. 0a). Wenn es sich um einen dreistelligen Code geht, werden zwei Buchstaben gefolgt von einer Ziffer (z. B. jp1) angezeigt. In allen Fällen wird 001 unmittelbar nach dem XX-Code angezeigt.


## <a name="voice-configuration-requirements"></a>Anforderungen an die Sprachkonfiguration

Wenn Benutzer für unternehmensweites Voice in lokal konfiguriert sind, müssen Sie die Aktualisierung ihrer Sprachkonfiguration koordinieren, wenn Sie sie ins Internet verschieben, oder Alternativ können Sie sie ohne Telefoniefunktionen migrieren. Die verfügbaren Optionen hängen davon ab, ob der Benutzer den Teams oder Skype for Business verwendet, sobald er online ist:

- Sie können den Telefonieanbieter eines Benutzers so aktualisieren, dass er einen [Microsoft-Anrufplan verwendet.](/microsoftteams/calling-plans-for-office-365) Dies ist eine Option, ob Benutzer Teams oder Skype for Business verwenden.
- Sie können weiterhin Ihren lokalen PSTN-Anbieter verwenden:
  - Sprachbenutzer, die die Teams verwenden, müssen für direktes [Routing konfiguriert werden.](/microsoftteams/direct-routing-plan) Direktes Routing ist nur verfügbar, nachdem der Benutzer von lokal in online verschoben wurde.
  - Sprachbenutzer, die den Skype for Business client verwenden, nachdem sie online verschoben wurden, müssen für die Skype for Business Hybrid konfiguriert werden.

Weitere Informationen zu Telefonieoptionen in Hybridumgebungen sowie eine Unterstützungsmatrix finden Sie unter Benutzerkonten in einer Hybridumgebung [mit PSTN-Konnektivität.](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment)

## <a name="other-considerations"></a>Andere Überlegungen

Die Richtlinien (z. B. die Kontrolle von Nachrichten, Besprechungen und Anrufverhalten) in lokalen und Online-Umgebungen sind unabhängig voneinander. Sie sollten erwägen, alle Richtlinien in der Umgebung zu konfigurieren und sie dem Benutzer zuzuordnen, bevor Sie diesen Benutzer von der lokalen in die Cloud verschieben, damit er die richtige Konfiguration hat, sobald er zu online migriert wird.

## <a name="see-also"></a>Siehe auch

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Einrichten von Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planen von direktem Routing](/microsoftteams/direct-routing-plan)

[Move-CsUser](/powershell/module/skype/move-csuser)
