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
description: 'Zusammenfassung: in einer lokalen Bereitstellung von Skype for Business Server, die für Hybrid aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud (ob Microsoft Teams oder Skype for Business Online) migrieren..'
ms.openlocfilehash: eede6062bd9d03a2d9d6062a6dacb861ce37e14c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221125"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud

Bei einer lokalen Bereitstellung von Skype for Business Server, die für Hybridnutzung aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud verschieben (entweder in Microsoft Teams oder in Skype for Business Online). Ob ein Benutzer lokal oder in der Cloud verwaltet wird, gibt das Skype for Business Home des Benutzer an:

- Benutzer, die lokal verwaltet werden, interagieren mit lokalen Skype for Business Servern.
- Online verwaltete Benutzer können mit Skype for Business-Onlinediensten interagieren.

*Microsoft Teams-Benutzer verfügen inhärent über ein Skype for Business Home, ganz gleich, ob sie Skype for Business verwenden oder nicht.* Wenn Sie lokale Skype for Business Benutzer haben, die auch Teams (nebeneinander) verwenden, werden diese Benutzer lokal verwaltet. Microsoft Teams-Benutzer mit Skype for Business lokal haben nicht die Möglichkeit, mit Skype for Business Benutzern Ihres Teams-Clients zusammenzuarbeiten, und Sie können auch nicht von Microsoft Teams mit Benutzern in einer Verbundorganisation kommunizieren. Solche Funktionen stehen nur zur Verfügung, nachdem der Benutzer von Skype for Business lokal in Online verschoben wurde. Wenn Sie einen Benutzer auf "Online" umstellen, können Sie ihm entweder die Verwendung von Skype for Business Online (und optional Teams) gestatten, oder Sie können ihm den TeamsOnly-Modus zuweisen. Wenn Ihre Organisation bereits Teams verwendet, wird dringend empfohlen, die Benutzer in den Teams Only-Modus zu verschieben. Dadurch wird sichergestellt, dass alle eingehenden Chats und Anrufe an ihren Team-Client weitergeleitet werden. Weitere Informationen finden Sie unter Microsoft [Teams Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence) -und [Migrations-und Interoperabilitäts Leit Faden für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Voraussetzungen

Voraussetzungen für die Verlagerung eines Benutzers in die Cloud (ob nur Skype for Business oder nur Teams-Modus):

- Die Organisation muss Azure AD Verbindung ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [configure Azure AD Connect](configure-azure-ad-connect.md)beschrieben.
- Skype for Business Hybrid muss konfiguriert sein, wie unter [configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md)beschrieben.
- Der Benutzer muss über eine Lizenz für Skype for Business Online (Plan 2) sowie, bei Verwendung von Teams, zudem über eine Teams-Lizenz verfügen.  Weitere Schritte:
    - Wenn der Benutzer für Einwahlkonferenzen in lokal aktiviert ist, muss der Benutzer standardmäßig auch über eine Audiokonferenz-Lizenz verfügen, die in Microsoft 365 oder Office 365 zugewiesen ist, bevor Sie den Benutzer online migrieren ausführen. Nach der Migration zur Cloud wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt. Wenn Sie einen Benutzer aus irgendeinem Grund in die Cloud umstellen, jedoch keine Audiokonferenzfunktionen verwenden möchten, können Sie diese Prüfung außer Kraft setzen, indem Sie den- `BypassAudioConferencingCheck` Parameter in angeben `Move-CsUser` .
    - Wenn der Benutzer für Enterprise-VoIP in lokal aktiviert ist, muss der Benutzer standardmäßig über eine Telefon System Lizenz verfügen, die in Microsoft 365 oder Office 365 zugewiesen ist, bevor Sie den Benutzer online migrieren. Nach der Migration zur Cloud wird der Benutzer für das Telefonsystem in der Cloud bereitgestellt. Wenn Sie einen Benutzer aus irgendeinem Grund in die Cloud umstellen, aber keine Telefon System Funktion verwenden möchten, können Sie diese Prüfung außer Kraft setzen, indem Sie den `BypassEnterpriseVoiceCheck` Parameter in angeben `Move-CsUser` .


## <a name="moving-users"></a>Verschieben von Benutzern

Wenn ein Benutzer aus der lokalen Umgebung in die Cloud verschoben wird:

- Der Benutzer beginnt für alle Skype for Business-Funktionen mit der Verwendung der Skype for Business Online-Dienste in der Cloud.
- Teams-Benutzer werden zur Interoperabilität mit Skype for Business-Benutzern aktiviert und können auch einen Verbund mit anderen Organisationen bilden.
- Kontakte von lokal werden in die Cloud verschoben (entweder Skype for Business oder Teams).
- Vorhandene Besprechungen, die Sie in der Zukunft geplant haben, werden in Online migriert: Wenn Benutzer direkt in TeamsOnly verschoben werden (siehe unten), werden Besprechungen in Teams-Besprechungen umgewandelt, andernfalls werden Besprechungen weiterhin Skype for Business, werden jedoch migriert, sodass Sie online statt lokal gehostet werden.  Die Migration von Besprechungen geschieht asynchron und beginnt ungefähr 90 Minuten nach dem Verschieben des Benutzers.  Den Status der Besprechungsmigration können Sie mit [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms) ermitteln. Bitte beachten Sie: Alle Inhalte, die im Vorfeld der Besprechung hochgeladen wurden, werden nicht verschoben.

Um Benutzer zwischen lokal und der Cloud zu verlagern (in Teams oder Skype for Business Online), verwenden Sie entweder das Cmdlet "CsUser" oder die Skype for Business-Verwaltungskonsole, beide lokale Tools. Diese Tools unterstützen drei unterschiedliche Pfade für die Migration:

- [Von Skype for Business Server (lokal) bis Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Von Skype for Business Server (lokal) direkt in Microsoft Teams](move-users-from-on-premises-to-teams.md) (und verschiebt Sie auch in Skype for Business Online).  Die Option zum direkten Wechsel von lokal in Teams ist in Skype for Business Server 2019 sowie Kumulatives Update 8 für Skype for Business Server 2015 verfügbar. Organisationen, die frühere Versionen von Skype for Business Server verwenden, können Benutzer in den TeamsOnly-Modus verschieben, indem sie sie zuerst zu Skype for Business Online migrieren und diesen Benutzern dann den TeamsOnly-Modus zuweisen, sobald Sie online sind.
- [Von Online (ob nur Teams oder nicht) bis lokal](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Erforderliche administrative Anmeldeinformationen

Um Benutzer zwischen lokal und der Cloud zu migrieren, müssen Sie ein Konto mit ausreichenden Berechtigungen sowohl in der lokalen Skype for Business Server Umgebung als auch in der Microsoft 365-oder Office 365-Organisation verwenden. Sie können entweder ein Konto verwenden, das über alle erforderlichen Berechtigungen verfügt, oder Sie können zwei Konten verwenden, in diesem Fall würden Sie mit lokalen Anmeldeinformationen auf die lokalen Tools zugreifen, und dann in diesen Tools zusätzliche Anmeldeinformationen für ein Microsoft 365-oder Office 365 Administratorkonto bereitstellen.  

- In der lokalen Umgebung muss der Benutzer, der die Migration ausführt, über die Rolle CSServerAdminstrator in Skype for Business Server verfügen.
- In Microsoft 365 und Office 365 muss der Benutzer, der die Migration ausführt, entweder ein globaler Administrator sein oder über Skype for Business Administrator-und Benutzeradministratorrollen verfügen.  

    > [!Important]
    > - Wenn Sie die Skype for Business-Verwaltungskonsole verwenden, werden Sie aufgefordert, Anmeldeinformationen für ein Microsoft 365-oder Office 365-Konto mit den entsprechenden Rollen anzugeben, wie oben beschrieben. Sie müssen ein Konto angeben, das in. onmicrosoft.com endet. Wenn dies nicht möglich ist, verwenden Sie das Cmdlet "CsUser".
    >- Wenn Sie CsUser in PowerShell verwenden, können Sie entweder ein Konto verwenden, das in. onmicrosoft.com endet, oder Sie können ein beliebiges lokales Konto verwenden, das mit Azure AD synchronisiert wird, vorausgesetzt, Sie geben auch den Parameter HostedMigrationOverrideUrl im Cmdlet an. Der Wert der URL für die Außerkraftsetzung der gehosteten Migration ist eine Variante der folgenden URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Ersetzen Sie in der obigen URL das XX durch zwei oder drei Zeichen, die wie folgt bestimmt werden:
    >   - Führen Sie in einer Skype for Business Online PowerShell-Sitzung das folgende Cmdlet aus:<br>`Get-CsTenant|ft identity`
    >    - Der resultierende Wert wird im folgenden Format sein:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Der zwei-oder dreistellige Code ist der im Abschnitt DC = lyncXX001 enthaltene XX. Wenn es sich um einen Code mit zwei Zeichen handelt, handelt es sich um eine Ziffer, gefolgt von einer Zahl (beispielsweise 0A). Wenn es sich um einen dreistelligen Code handelt, werden zwei Buchstaben gefolgt von einer Ziffer (beispielsweise JP1). In allen Fällen sehen Sie 001 unmittelbar nach dem XX-Code.


## <a name="voice-configuration-requirements"></a>Anforderungen an die Sprachkonfiguration

Wenn Benutzer für Enterprise-VoIP in lokal konfiguriert sind, müssen Sie die Aktualisierung Ihrer VoIP-Konfiguration koordinieren, wenn Sie Sie in Online verschieben, oder Sie können Sie auch ohne Telefonfunktionen migrieren. Die verfügbaren Optionen hängen davon ab, ob der Benutzer die Teams oder Skype for Business-Client verwendet, sobald er online ist:

- Sie können den Telefonanbieter eines Benutzers so aktualisieren, dass er einen [Microsoft-Anrufplan](/microsoftteams/calling-plans-for-office-365)verwendet. Diese Option wird verwendet, wenn Benutzer Teams oder Skype for Business-Clients verwenden.
- Sie können weiterhin ihren lokalen PSTN-Anbieter verwenden:
  - VoIP-Benutzer, die Microsoft Teams verwenden, müssen für das [direkte Routing](/microsoftteams/direct-routing-plan)konfiguriert sein. Das direkte Routing ist nur verfügbar, nachdem der Benutzer von lokal in Online verschoben wurde.
  - VoIP-Benutzer, die den Skype for Business-Client verwenden, nachdem Sie Online verschoben wurden, müssen für Skype for Business Hybrid VoIP-Funktionalität konfiguriert sein.

Weitere Informationen zu den Telefoniefunktionen in Hybrid Umgebungen sowie eine Unterstützungsmatrix finden Sie unter [Benutzerkonten in einer Hybridumgebung mit PSTN-Konnektivität](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Andere Überlegungen

Die Richtlinien (z. B. die Kontrolle von Nachrichten, Besprechungen und Anrufverhalten) in lokalen und Online-Umgebungen sind unabhängig voneinander. Möglicherweise möchten Sie in der Lage sein, alle Richtlinien in der Umgebung zu konfigurieren und Sie dem Benutzer zuzuweisen, bevor Sie diesen Benutzer von lokal in die Cloud migrieren, sodass diese die richtige Konfiguration haben, sobald Sie zu Online migriert werden.

## <a name="see-also"></a>Siehe auch

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Microsoft Teams](move-users-from-on-premises-to-teams.md)

[Einrichten von Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planen von direktem Routing](/microsoftteams/direct-routing-plan)

[CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
