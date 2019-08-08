---
title: Upgrade von Skype for Business Online auf Microsoft Teams | Bereitstellen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Überlegungen zum Upgrade auf Teams von Skype for Business Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f4a7076a5911798664ea1b7668e7dee8c820ff1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235861"
---
![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Bereitstellung und Implementierung] (media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")

Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ihre Projekt Beteiligten wurden eingetragen](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Verständliche Koexistenz und Interoperabilität von Skype for Business und Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ihre Upgrade-Reise gewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Ihre Umgebung vorbereitet](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Vorbereiten Ihrer Organisation](https://aka.ms/SkypeToTeams-UserReadiness)
- [Durchgeführt eines Pilotprojekts](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Upgrade von Skype for Business Online auf Microsoft Teams

Befolgen Sie die Anleitungen in diesem Artikel, wenn Sie Skype for Business Online vollständig bereitgestellt haben und Ihre Benutzer von Skype for Business auf Teams aktualisieren möchten. Sie können Benutzer auf der Grundlage der von Ihrer Organisation ausgewählten Upgrade-Reise selektiv oder vollständig aktualisieren, indem Sie Ihren Benutzern den entsprechenden Koexistenz-und Aktualisierungsmodus zuweisen.

> [!IMPORTANT]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, danach wird es nicht mehr barrierefrei oder unterstützt. Um die Leistung zu maximieren und sicherzustellen, dass Ihre Organisation die richtige Zeit für die Implementierung Ihres Upgrades hat, empfehlen wir Ihnen, Ihre Reise zu Microsoft Teams heute zu beginnen. Beachten Sie, dass ein erfolgreiches Upgrade die technische und Benutzer Bereitschaft ausrichtet, damit Sie die hierin beschriebenen Anleitungen für die Navigation in Ihrer Reise zu Microsoft Teams nutzen können.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Zuweisen des Koexistenz-und Aktualisierungsmodus

Sie können Ihre Benutzer auf den TeamsOnly-Modus aktualisieren, indem Sie die UpgradeToTeams-Instanz von TeamsUpgradePolicy zuweisen, die mithilfe des Microsoft Teams admin Centers oder einer Skype for Business-Remote-Windows PowerShell-Sitzung ausgeführt werden kann. Sie können dies entweder auf Benutzerbasis oder auf Mandantenebene tun, wenn Sie den gesamten Mandanten in einem Schritt aktualisieren möchten. 

Weitere Informationen finden Sie unter [Festlegen von Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Gleichzeitiges Aktualisieren aller Benutzer auf Teams

Führen Sie die folgenden Schritte aus, um alle Benutzer gleichzeitig auf Teams zu aktualisieren.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Schritt 1: Benachrichtigen der Benutzer über die Änderung (optional)

1. Wählen Sie im Microsoft Teams Admin Center die Option **organisationsweite Einstellungen** > **Teams Upgrade**aus.
2. Ändern Sie unter **Koexistenzmodus**die Option **Skype for Business-Benutzer benachrichtigen, dass ein Upgrade auf Teams verfügbar ist** , auf ein. ****

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Schritt 2: Festlegen des Koexistenzmodus auf "TeamsOnly" für die Organisation

1. Wählen Sie im Microsoft Teams Admin Center die Option **organisationsweite Einstellungen**aus.
2. Wählen Sie in der Dropdownliste **Koexistenzmodus** den Modus **nur Teams** aus.

## <a name="upgrade-users-in-stages"></a>Stufenweises Aktualisieren von Benutzern

Führen Sie die folgenden Schritte aus, wenn Sie Ihre Benutzer schrittweise auf TeamsOnly upgraden möchten.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Schritt 1: Identifizieren von Benutzergruppen für ein Upgrade

Oft können Organisationen beschließen, ihre Organisationen in Erfolgs Wellen von Benutzern zu aktualisieren.  Sie sollten diese Benutzer zuerst identifizieren, damit Sie im Microsoft Teams Admin Center einfach nach diesen Benutzern suchen können. Alternativ können Sie PowerShell verwenden, um dies effizienter zu gestalten. Nachdem Sie die Gruppe der Benutzer für eine bestimmte Upgrade-Welle identifiziert haben, fahren Sie mit den restlichen Schritten fort.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Schritt 2: Einrichten der Benachrichtigung für die Benutzer in der aktuellen Aktualisierungs Welle (optional)

Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:
1. Wählen Sie im Microsoft Teams Admin Center die Option **Benutzer**aus, und wählen Sie das Kontrollkästchen für bis zu 20 Benutzer aus, die aktualisiert werden sollen. 
2. Wählen Sie in der oberen linken Ecke der ListView die Option **Einstellungen bearbeiten** aus. 
3. Ändern Sie im Bereich **Bearbeitungseinstellungen** auf der rechten Seite unter **Teams**-Upgrade **die Option Skype for Business-Benutzer** auf **ein**umschalten. Hinweis: Wenn der Wert des Koexistenzmodus "org-Wide-Einstellungen verwenden" lautet, wird dieser Schalter nicht angezeigt, daher müssen Sie zuerst explizit den Koexistenzmodus für diese Benutzer auf den Standardwert für die Organisation festlegen.

Alternativ können Sie es einfacher finden, Benachrichtigungen für Gruppen von Benutzern gleichzeitig mithilfe von PowerShell zu aktivieren. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Schritt 3: Einrichten des Koexistenzmodus für Benutzer nur für Teams

Wenn Sie bereit sind, die Benutzer in der aktuellen Welle zu aktualisieren, um Teams als ihre einzige Anwendung zu verwenden, legen Sie den Koexistenzmodus für die Benutzer nur auf Teams fest.

Wenn Sie das Microsoft Teams Admin Center verwenden, können Sie TeamsUpgradePolicy für bis zu 20 Benutzer gleichzeitig konfigurieren:
1. Wählen Sie im Microsoft Teams Admin Center die Option **Benutzer**aus, und aktivieren Sie dann das Kontrollkästchen für bis zu 20 Benutzer.
2. Wählen Sie in der oberen linken Ecke der ListView die Option **Einstellungen bearbeiten** aus.
3. Legen Sie im Bereich " **Einstellungen bearbeiten** " auf der rechten Seite unter " **Teams-Upgrade** " den Koexistenzmodus nur in der Dropdownliste auf " **Teams** " fest.

Alternativ können Sie es einfacher finden, Gruppen von Benutzern gleichzeitig mithilfe von PowerShell zu aktualisieren. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Schritt 4: Wiederholen Sie die Schritte 1-3 für aufeinander folgende Wellen von Benutzern.

Wiederholen Sie die vorherigen Schritte, um TeamsOnly auf weitere Benutzer anzuwenden, während Sie Ihr Upgrade auf den Modus nur für Teams überprüfen und bereit zum Erweitern sind.  


## <a name="phone-system-and-teams-upgrade"></a>Upgrade für Telefonsysteme und Teams

Wenn Ihre Skype for Business Online-Bereitstellung Telefon System mit Anrufplänen umfasst und Microsoft Ihr PSTN-Anbieter (Public Switched Telephone Network) ist, wird durch das Upgrade Ihrer Benutzer auf Teams automatisch ein eingehender PSTN-Anruf an Teams weitergeleitet.

Wenn Ihre Skype for Business Online-Bereitstellung das Telefonsystem mit Cloud Connector Edition umfasst, lesen Sie die [zusätzlichen Überlegungen zur direkten Weiterleitung von Telefonsystemen](2-envision-make-my-service-decisions-direct-routing.md).
