---
title: Migrieren von Benutzern zwischen lokal und Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
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
ms.openlocfilehash: b7e3ecc46af5a3043848d9291394c0bff7835883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160570"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Migrieren von Benutzern zwischen lokal und Cloud

In einer lokalen Bereitstellung von Skype for Business Server, die für Hybrid aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud (ob Microsoft Teams oder Skype for Business Online) migrieren. Unabhängig davon, ob sich ein Benutzer lokal oder in der Cloud befindet, wird als Skype for Business-Startseite des Benutzers bezeichnet:

- Benutzer, die lokal verwaltet werden, interagieren mit lokalen Skype for Business Servern.
- Benutzer, die Online verwaltet werden, können mit Skype for Business Online Dienst interagieren.

*Microsoft Teams-Benutzer haben inhärent eine Skype for Business Heimat, unabhängig davon, ob Sie Skype for Business verwenden oder nicht.* Wenn Sie lokale Skype for Business Benutzer haben, die auch Teams (nebeneinander) verwenden, werden diese Benutzer lokal verwaltet. Microsoft Teams-Benutzer mit Skype for Business lokal haben nicht die Möglichkeit, mit Skype for Business Benutzern Ihres Teams-Clients zusammenzuarbeiten, und Sie können auch nicht von Microsoft Teams mit Benutzern in einer Verbundorganisation kommunizieren. Solche Funktionen stehen nur zur Verfügung, nachdem der Benutzer von Skype for Business lokal in Online verschoben wurde. Wenn Sie einen Benutzer in den Onlinebetrieb versetzen, können Sie ihm entweder die Verwendung Skype for Business Online (und optional auch von Microsoft Teams) ermöglichen, oder Sie können ihn nur für Teams bereitstellen. Wenn Ihre Organisation bereits Teams verwendet, wird dringend empfohlen, dass Sie Sie in den Modus "nur Teams" umstellen, wodurch sichergestellt ist, dass alle eingehenden Chats und Anrufe in Ihrem Microsoft Teams-Client weitergeleitet werden. Weitere Informationen finden Sie unter Microsoft [Teams Koexistenz mit Skype for Business](/microsoftteams/coexistence-chat-calls-presence) -und [Migrations-und Interoperabilitäts Leit Faden für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Voraussetzungen

Voraussetzungen für die Verlagerung eines Benutzers in die Cloud (ob nur Skype for Business oder nur Teams-Modus):

- Die Organisation muss Azure AD Verbindung ordnungsgemäß konfiguriert haben und alle relevanten Attribute für den Benutzer synchronisieren, wie unter [configure Azure AD Connect](configure-azure-ad-connect.md)beschrieben.
- Skype for Business Hybrid muss konfiguriert sein, wie unter [configure Skype for Business Hybrid](configure-federation-with-skype-for-business-online.md)beschrieben.
- Dem Benutzer muss eine Lizenz für Skype for Business Online (Plan 2) zugewiesen sein, und wenn er Teams verwenden wird, muss er auch über eine Microsoft Teams-Lizenz verfügen.  Weitere Schritte:
    - Wenn der Benutzer für Einwahlkonferenzen in lokal aktiviert ist, muss dem Benutzer standardmäßig auch eine Audiokonferenz-Lizenz in Office 365 zugewiesen sein, bevor Sie den Benutzer online verlegen ausführen. Nachdem der Benutzer in die Cloud migriert wurde, wird er für Audiokonferenzen in der Cloud eingerichtet. Wenn Sie einen Benutzer aus irgendeinem Grund in die Cloud umstellen, jedoch keine Audiokonferenzfunktionen verwenden möchten, können Sie diese Prüfung außer Kraft setzen, `BypassAudioConferencingCheck` indem Sie `Move-CsUser`den-Parameter in angeben.
    - Wenn der Benutzer für Enterprise-VoIP in lokal aktiviert ist, muss der Benutzer standardmäßig über eine Telefon System Lizenz verfügen, die in Office 365 zugewiesen ist, bevor Sie den Benutzer online verlagern. Nachdem der Benutzer in die Cloud migriert wurde, wird er für das Telefon System in der Cloud eingerichtet. Wenn Sie einen Benutzer aus irgendeinem Grund in die Cloud umstellen, aber keine Telefon System Funktion verwenden möchten, können Sie diese Prüfung außer Kraft setzen `BypassEnterpriseVoiceCheck`, indem `Move-CsUser`Sie den Parameter in angeben.


## <a name="moving-users"></a>Verschieben von Benutzern

Wenn ein Benutzer von lokal in die Cloud verschoben wird:

- Der Benutzer beginnt mit der Verwendung von Skype for Business Online Diensten in der Cloud für alle Skype for Business Funktionen.
- Microsoft Teams-Benutzer werden für die Interoperabilität mit Skype for Business Benutzern aktiviert, und Sie können auch mit anderen Organisationen in einen Verbund eintreten.
- Kontakte von lokal werden in die Cloud verschoben (entweder Skype for Business oder Teams).
- Vorhandene Besprechungen, die Sie in der Zukunft geplant haben, werden in Online migriert: Wenn Benutzer direkt in TeamsOnly verschoben werden (siehe unten), werden Besprechungen in Teams-Besprechungen umgewandelt, andernfalls werden Besprechungen weiterhin Skype for Business, aber migriert, sodass Sie Online gehostet statt lokal.  Die Migration von Besprechungen erfolgt asynchron und beginnt etwa 90 Minuten nach dem Verschieben des Benutzers.  Zum Bestimmen des Status der Besprechungs Migration können Sie [Get-csMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)verwenden. Beachten Sie, dass alle Inhalte, die im Vorfeld der Besprechung hochgeladen wurden, nicht verschoben werden.

Um Benutzer zwischen lokal und der Cloud zu verlagern (in Teams oder Skype for Business Online), verwenden Sie entweder das Cmdlet "CsUser" oder die Skype for Business-Verwaltungskonsole, beide lokale Tools. Diese Tools unterstützen drei verschiedene Pfade zum verlegen:

- [Von Skype for Business Server (lokal) bis Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Von Skype for Business Server (lokal) direkt in Microsoft Teams](move-users-from-on-premises-to-teams.md) (und verschiebt Sie auch in Skype for Business Online).  Die Option zum direkten Wechsel von lokal in Teams ist in Skype for Business Server 2019 sowie Kumulatives Update 8 für Skype for Business Server 2015 verfügbar. Organisationen, die frühere Versionen von Skype for Business Server verwenden, können Benutzer nur in Microsoft Teams verschieben, indem Sie Sie zuerst in Skype for Business Online verschieben und anschließend den TeamsOnly-Modus auf diese Benutzer anwenden, sobald Sie online sind.
- [Von Online (ob nur Teams oder nicht) bis lokal](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Erforderliche administrative Anmeldeinformationen

Um Benutzer zwischen lokal und der Cloud zu migrieren, müssen Sie ein Konto mit ausreichenden Berechtigungen sowohl in der lokalen Skype for Business Server Umgebung als auch im Office 365 Mandanten verwenden. Sie können entweder ein Konto verwenden, das über alle erforderlichen Berechtigungen verfügt, oder Sie können zwei Konten verwenden, in diesem Fall würden Sie mit lokalen Anmeldeinformationen auf die lokalen Tools zugreifen, und dann in diesen Tools zusätzliche Anmeldeinformationen für eine Office 365 bereitstellen. Administratorkonto.  

- In der lokalen Umgebung muss der Benutzer, der die Bewegung ausführt, über die Rolle CSServerAdminstrator in Skype for Business Server verfügen.
- In Office 365 muss der Benutzer, der die Bewegung ausführt, entweder ein globaler Administrator sein oder über Skype for Business Administrator-und Benutzeradministratorrollen verfügen.  

    > [!Important]
    > - Wenn Sie die Skype for Business-Verwaltungskonsole verwenden, werden Sie aufgefordert, Anmeldeinformationen für ein Office 365 Konto mit den entsprechenden Rollen anzugeben, wie oben beschrieben. Sie müssen ein Konto angeben, das in. onmicrosoft.com endet. Wenn dies nicht möglich ist, verwenden Sie das Cmdlet "CsUser".
    >- Wenn Sie CsUser in PowerShell verwenden, können Sie entweder ein Konto verwenden, das in. onmicrosoft.com endet, oder Sie können ein beliebiges lokales Konto verwenden, das mit Azure AD synchronisiert wird, vorausgesetzt, Sie geben auch den Parameter HostedMigrationOverrideUrl im Cmdlet an. . Der Wert der URL für die Außerkraftsetzung der gehosteten Migration ist eine Variante der folgenden URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Ersetzen Sie in der obigen URL das XX durch zwei oder drei Zeichen, die wie folgt bestimmt werden:
    >   - Führen Sie in einer Skype for Business Online PowerShell-Sitzung das folgende Cmdlet aus:<br>`Get-CsTenant|ft identity`
    >    - Der resultierende Wert wird im folgenden Format sein:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Der zwei-oder dreistellige Code ist der im Abschnitt DC = lyncXX001 enthaltene XX. Wenn es sich um einen Code mit zwei Zeichen handelt, handelt es sich um eine Ziffer, gefolgt von einer Zahl (beispielsweise 0A). Wenn es sich um einen dreistelligen Code handelt, werden zwei Buchstaben gefolgt von einer Ziffer (beispielsweise JP1). In allen Fällen sehen Sie 001 unmittelbar nach dem XX-Code.


## <a name="voice-configuration-requirements"></a>Anforderungen an die Sprachkonfiguration

Wenn Benutzer für Enterprise-VoIP in lokal konfiguriert sind, müssen Sie die Aktualisierung Ihrer VoIP-Konfiguration koordinieren, wenn Sie Sie in Online verschieben, oder Sie können Sie auch ohne Telefonfunktionen migrieren. Die verfügbaren Optionen hängen davon ab, ob der Benutzer die Teams oder Skype for Business-Client verwendet, sobald er online ist:

- Sie können den Telefonanbieter eines Benutzers so aktualisieren, dass er einen [Microsoft](/microsoftteams/calling-plans-for-office-365)-Anrufplan verwendet. Diese Option wird verwendet, wenn Benutzer Teams oder Skype for Business-Clients verwenden.
- Sie können weiterhin ihren lokalen PSTN-Anbieter verwenden:
  - VoIP-Benutzer, die Microsoft Teams verwenden, müssen für das [direkte Routing](/microsoftteams/direct-routing-plan)konfiguriert sein. Das direkte Routing ist nur verfügbar, nachdem der Benutzer von lokal in Online verschoben wurde.
  - VoIP-Benutzer, die den Skype for Business-Client verwenden, nachdem Sie Online verschoben wurden, müssen für Skype for Business Hybrid VoIP-Funktionalität konfiguriert sein.

Weitere Informationen zu den Telefoniefunktionen in Hybrid Umgebungen sowie eine Unterstützungsmatrix finden Sie unter [Benutzerkonten in einer Hybridumgebung mit PSTN-Konnektivität](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Weitere Aspekte

Die Richtlinien (beispielsweise zum Steuern von Messaging-, Besprechungs-und Anrufverhalten) in lokalen und Online Umgebungen sind unabhängig. Möglicherweise möchten Sie in der Lage sein, alle Richtlinien in der Umgebung zu konfigurieren und Sie dem Benutzer zuzuweisen, bevor Sie diesen Benutzer von lokal in die Cloud migrieren, sodass diese die richtige Konfiguration haben, sobald Sie zu Online migriert werden.

## <a name="see-also"></a>Siehe auch

[Migrieren von Benutzern von lokal in Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Migrieren von Benutzern von lokalen zu Teams](move-users-from-on-premises-to-teams.md)

[Einrichten des Besprechungs Migrations Diensts (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planen des direkten Routings](/microsoftteams/direct-routing-plan)

[CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
