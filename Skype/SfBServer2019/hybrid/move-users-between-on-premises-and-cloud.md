---
title: Verschieben von Benutzern zwischen lokalen und cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Zusammenfassung: In einer lokalen Bereitstellung von Skype für Business Server, die für hybride aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud (an, ob Microsoft-Teams oder Skype für Business Online) verschieben.'
ms.openlocfilehash: 492a2a7d14af77bc0b90afe03f0d36de0f830129
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247670"
---
# <a name="move-users-between-on-premises-and-cloud"></a>Verschieben von Benutzern zwischen lokalen und cloud

In einer lokalen Bereitstellung von Skype für Business Server, die für hybride aktiviert ist, können Sie Benutzer zwischen der lokalen Umgebung und der Cloud (an, ob Microsoft-Teams oder Skype für Business Online) verschieben. Ob ein Benutzer befindet (lokal) oder in der Cloud als Skype für Business privat-des Benutzers bezeichnet wird:

- Benutzer, die lokal verwaltet werden interagieren mit lokalen Skype für Unternehmensserver.
- Benutzer, die online verwaltet werden möglicherweise Skype für Business Onlinedienst interagieren.

*Teams Benutzer haben grundsätzlich einen Skype für Business Ihnen zu Hause, ob sie Skype für Unternehmen oder nicht verwenden.* Wenn Sie lokale Skype für Unternehmensbenutzer, die auch Teams (nebeneinander) verwenden verfügen, werden diese Benutzer lokal verwaltet. Teams Benutzer mit Skype für Unternehmen lokal müssen nicht die Möglichkeit für die Zusammenarbeit mit Skype für Unternehmensbenutzer von ihrem Client Teams, noch können sie kommunizieren von Teams mit Benutzern in einer verbundenen Organisation. Diese Funktionalität ist nur verfügbar, wenn der Benutzer von Skype für Unternehmen lokal zu online verschoben wird. Wenn Sie einen Benutzer zu online verschieben, Sie können entweder Skype für Business Online (und optional Teams) verwenden, oder können Sie diese Teams nur stellen. Wenn Ihre Organisation bereits Teams verwendet wird, wird empfohlen, dass Sie sie in den Modus nur Teams, um sicherzustellen verschieben, dass alle eingehenden Chats und Anrufe routing in ihren Teams Client kommt. Weitere Informationen finden Sie unter [Teams Koexistenz mit Skype für Unternehmen](/microsoftteams/coexistence-chat-calls-presence) und [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

## <a name="prerequisites"></a>Voraussetzungen

Erforderliche Komponenten zum Verschieben eines Benutzers in die Cloud (ob Skype für Business nur oder Teams nur Modus):

- Die Organisation benötigen Azure AD-Connect ordnungsgemäß konfiguriert und synchronisiert werden alle relevanten Attribute für den Benutzer, wie beschrieben unter [Konfigurieren von Azure AD-Verbindung](configure-azure-ad-connect.md).
- Skype für hybride Business muss konfiguriert werden, wie beschrieben in [Skype für hybride Business konfigurieren](configure-federation-with-skype-for-business-online.md).
- Der Benutzer muss zugewiesen werden keine Lizenz für Skype für Business Online (Plan 2), und wenn sie Teams verwenden, müssen sie auch eine Lizenz Teams besitzen.  Außerdem:
    - Wenn der Benutzer für einwahlkonferenzen in lokal, standardmäßig aktiviert wird der Benutzer auch in Office 365 zugewiesen wird, vor dem Ausführen eine Audiokonferenz-Lizenz verfügen muss verschoben der Benutzer online. Nachdem die Cloud migriert werden, wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt werden. Wenn einige Grund Sie Verschieben eines Benutzers in der Cloud, aber nicht audiokonferenzfunktionen verwenden möchten, können Sie dieses Kontrollkästchen durch Angeben von Überschreiben der `BypassAudioConferencingCheck` -Parameter im `Move-CsUser`.
    - Wenn der Benutzer für Enterprise-VoIP in lokal aktiviert ist, standardmäßig benötigen der Benutzer eine Telefonsystem Lizenz in Office 365 zugewiesen werden, bevor Sie den Benutzer online verschieben. Nachdem für Telefonsystem in der Cloud migriert in die Cloud, die Benutzer bereitgestellt wird. Wenn einige Grund Sie Verschieben eines Benutzers in die Cloud jedoch Telefonsystem-Funktionalität nicht verwenden möchten, können Sie dieses Kontrollkästchen durch Angeben von Überschreiben der `BypassEnterpriseVoiceCheck`-Parameter im `Move-CsUser`.


## <a name="moving-users"></a>Verschieben von Benutzern

Wenn ein Benutzer lokal in der Cloud verschoben wird:

- Der Benutzer beginnt mit Skype für Business Online-Dienste in der Cloud für alle Skype für Business-Funktionalität.
- Werden Benutzer des Teams für Unternehmensbenutzer für die Interoperabilität mit Skype aktiviert, und sie können auch Verbund mit anderen Organisationen.
- Kontakte aus lokal werden in der Cloud (Skype für Unternehmen) oder Teams verschoben.
- Vorhandene Besprechungen Organisation, die in der Zukunft geplant sind, werden in online migriert. Migration von Besprechungen erfolgt asynchron und etwa 90 Minuten nach dem Verschieben des Benutzers beginnt.  Um den Status des meeting-Migration zu ermitteln, können Sie [Get-CsMeetingMigrationStatus](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#managing-mms)verwenden. Beachten Sie, dass alle Inhalte, die vor der Besprechung hochgeladen wurde nicht verschoben wird.

Verschieben von Benutzern zwischen lokalen und der Cloud (an, ob Teams oder Skype für Online Business), verwenden Sie das Cmdlet Move-CsUser oder die Skype für Business Admin-Systemsteuerung, sind beide lokalen Tools. Diese Tools unterstützt drei verschiedene Move Pfade:

- [Von Skype für Business Server (lokal) auf Skype für Business Online](move-users-from-on-premises-to-skype-for-business-online.md).
- [Von Skype für Business Server (lokal) direkt auf nur Teams](move-users-from-on-premises-to-teams.md) (die auch an Skype für Business Online verschiebt).  Die Möglichkeit, Teams nur lokal direkt aus verschieben ist in Skype für Business Server 2019 als auch für kumulative Update 8 für Skype für Business Server 2015 verfügbar. Organisationen, die mit früheren Versionen von Skype für Business Server können Benutzer nur Teams durch Verschieben ersten herausgenommen Skype für Business Online, und klicken Sie dann den TeamsOnly Modus für diesen Benutzer anwenden, sobald sie online sind.
- [Von online (, ob nur oder nicht-Teams), zu lokal](move-users-from-the-cloud-to-on-premises.md).

## <a name="required-administrative-credentials"></a>Administratorrechte erforderlich

Um Benutzer zwischen lokalen und der Cloud zu verschieben, müssen Sie ein Konto mit den erforderlichen Berechtigungen in beiden der lokalen Skype für Business Server Umgebung sowie die Office 365-Mandanten verwenden. Können entweder ein Konto, das über die notwendigen Berechtigungen verfügt oder können zwei Konten, in diesem Fall Sie zugreifen würden die lokale-Tools mit lokalen Anmeldeinformationen, und klicken Sie dann in diese Tools würde Geben Sie zusätzliche Anmeldeinformationen für ein Office 365 Administratorkonto.  

- In der lokalen Umgebung muss der Benutzer, die die Verschiebung die CSServerAdminstrator Rolle in Skype für Business Server verfügen.
- In Office 365 der Benutzer die Verschiebung muss ein globaler Administrator sein, oder benötigen sie beide Skype für Business Administrator- und Rollen.  

    > [!Important]
    > - Wenn Sie die Skype für Business Admin-Systemsteuerung verwenden, werden Sie aufgefordert, Anmeldeinformationen für ein Office 365-Konto mit den entsprechenden Rollen, wie oben beschrieben werden. Sie müssen ein Konto, das in endet angeben. "onmicrosoft.com" dargestellt. Wenn dies nicht möglich ist, verwenden Sie das Move-CsUser-Cmdlet.
    >- Wenn Sie die Move-CsUser in PowerShell verwenden, können Sie entweder ein Konto, das in endet verwenden. "onmicrosoft.com", oder Sie können eine beliebige lokale Konto, das in Azure AD synchronisiert wird vorausgesetzt, dass Sie auch den Parameter HostedMigrationOverrideUrl im Cmdlet angeben . Der Wert der gehosteten Migration Außerkraftsetzung URL ist ein Variant-Wert mit der folgenden URL:https://adminXX.online.lync.com/HostedMigration/hostedmigrationService.svc<br>Ersetzen Sie in der oben genannten URL die XX mit zwei oder drei Zeichen, die wie folgt bestimmt:
    >   - Führen Sie in einer Skype für Business Online-PowerShell-Sitzung das folgende Cmdlet aus:<br>`Get-CsTenant|ft identity`
    >    - Der resultierende Wert wird in folgendem Format sein:<br>`OU=<guid>,OU=OCS Tenants,DC=lyncXX001,DC=local`
    >    - Der Code oder dreistellige befindet sich der XX enthalten sind, klicken Sie im Abschnitt DC = lyncXX001. Wenn es sich um einen zweistelligen Code ist, werden eine Ziffer, gefolgt von einer Zahl (beispielsweise 0a). Wenn es sich um einen dreistelligen Code ist, werden zwei Buchstaben gefolgt von einer Ziffer (beispielsweise jp1). In allen Fällen sehen Sie 001 unmittelbar hinter dem Code XX.


## <a name="voice-configuration-requirements"></a>Anforderungen für die VoIP-Konfiguration

Wenn Benutzer für Enterprise-VoIP in lokal konfiguriert sind, müssen Sie ihre VoIP-Konfiguration aktualisieren, wenn Sie diese in online verschieben oder alternativ Sie sie ohne Telefoniefunktionen migrieren konnte koordinieren. Die verfügbaren Optionen hängen davon ab, ob der Benutzer verwendet die Teams oder Skype für Business-Client, sobald sie online sind:

- Sie können Telefonieanbieter eine [Microsoft aufrufen Planen der](/microsoftteams/calling-plans-for-office-365)Verwendung eines Benutzers aktualisieren. Dies ist eine Option, ob Benutzer Teams oder Skype für Business Clients verwenden.
- Sie können auch weiterhin mithilfe Ihrer lokalen PSTN-Dienstanbieter:
  - VoIP-Benutzer, die Teams nutzen werden müssen für das [Direkte Routing](/microsoftteams/direct-routing-plan)konfiguriert werden. Direktes Routing ist nur verfügbar, nachdem der Benutzer von lokal zu online verschoben wird.
  - VoIP-Benutzer, die die Skype für Business-Client verwendet werden, nachdem sie online verschoben werden, müssen für Skype Business Hybrid-VoIP-Funktionen, konfiguriert werden.

Weitere Informationen zu den Telefonieoptionen in hybridumgebungen als auch eine unterstützbarkeitsmatrix finden Sie unter [Benutzerkonten in einer hybridumgebung mit PSTN-Anbindung](/microsoftteams/direct-routing-user-accounts-in-a-hybrid-environment).

## <a name="other-considerations"></a>Weitere Überlegungen

Die Richtlinien (z. B. für messaging, der Einhaltung und Aufrufen von Verhalten steuern) in lokalen und online sind Umgebungen unabhängig. Sie möchten berücksichtigen Konfigurieren von Richtlinien in der Umgebung und dem Benutzer zuweisen, bevor Sie dieses Benutzers lokal in der Cloud verschieben, damit sie die richtige Konfiguration besitzen, sobald sie Online migriert werden.

## <a name="see-also"></a>Siehe auch

[Verschieben von Benutzern aus der lokalen Bereitstellung nach Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md)

[Verschieben von Benutzern von lokalen Teams](move-users-from-on-premises-to-teams.md)

[Einrichten des Meeting Migration Service (MMS)](../../SfbOnline/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md)

[Planen von direktem Routing](/microsoftteams/direct-routing-plan)

[Move-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)