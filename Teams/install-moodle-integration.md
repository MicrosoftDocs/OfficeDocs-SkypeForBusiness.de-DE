---
title: Installieren der Moodle-Integration in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Moodle Open-Source Learning Management System (LMS)-app für Microsoft Teams installieren und konfigurieren.
keywords: Integration des Plugins für Moodle-Apps für Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd680cda5daeb5acebac8b8276e1adb86fdb563
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638534"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installieren der Moodle-Integration in Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), das beliebteste und Open-Source Learning Management System (LMS) weltweit, ist jetzt in Microsoft Teams integriert! Diese Integration hilft Pädagogen und Lehrern bei der Zusammenarbeit an Moodle-Kursen, stellen Sie Fragen zu Ihren Noten und Aufgaben, und bleiben Sie mit Benachrichtigungen auf dem laufenden – direkt in Teams!

Um IT-Administratoren zu helfen, diese Integration auf einfache Weise einzurichten, haben wir unser Open-Source-Moodle-Plug-in mit den folgenden Funktionen aktualisiert:

* Automatische Registrierung Ihres Moodle-Servers mit Azure AD.
* Bereitstellung mit einem Mausklick für Ihren Moodle Assistant-bot zu Azure.
* Automatische Bereitstellung von Teams und automatische Synchronisierung von Team Einschreibungen für alle oder ausgewählte Moodle-Kurse.
* Automatische Installation des Moodle-Reiters und des Moodle Assistant-bot in jedem synchronisierten Team. (In Kürze verfügbar)
* Veröffentlichen Sie die Moodle-App mit einem Mausklick in Ihrem privaten Teams-App Store. (In Kürze verfügbar)

Weitere Informationen zu den Funktionen, die diese Integration bietet, finden Sie [hier](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle).

## <a name="prerequisites"></a>Voraussetzungen

Um diese Anwendung installieren und konfigurieren zu können, benötigen Sie:

1. Moodle-Administratoranmeldeinformationen
2. Azure AD-Administratoranmeldeinformationen
3. Ein Azure-Abonnement, in dem Sie neue Ressourcen erstellen können

## <a name="step-1-install-the-moodle-plugin"></a>Schritt 1: Installieren des Moodle-Plugins

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Die Moodle-Integration in Microsoft Teams wird vom Open-Source- [Plugin für Moodle](https://github.com/Microsoft/o365-moodle)unterstützt. So installieren Sie das Plug-in auf Ihrem Moodle-Server:

1. Laden Sie zuerst das [Moodle-Plugin-Paket](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) herunter und speichern Sie es auf Ihrem lokalen Computer. Sie müssen Version 3,5 oder höher verwenden.
    * Wenn Sie das local_o365-Plugin installieren, werden auch die [auth_oidc](https://moodle.org/plugins/auth_oidc) -und [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) -Plugins installiert.
1. Melden Sie sich als Administrator bei Ihrem Moodle-Server an und wählen Sie im linken Navigationsbereich **Websiteverwaltung** aus.
1. Wählen Sie die Registerkarte **Plugins** aus, und klicken Sie dann auf **Plugins installieren**.
1. Klicken Sie im Abschnitt **Plugin aus ZIP-Datei installieren** auf die Schaltfläche **Datei auswählen** .
1. Wählen Sie im linken Navigationsbereich die Option **Datei hochladen** aus, suchen Sie nach der Datei, die Sie oben heruntergeladen haben, und klicken Sie auf **Diese Datei hochladen**.
1. Wählen Sie die Option **Websiteverwaltung** im linken Navigationsbereich erneut aus, um zu Ihrem Administrator Dashboard zurückzukehren. Scrollen Sie nach unten zu den **lokalen Plugins** , und klicken Sie auf den **Microsoft Office 365-Integrations** Link. Lassen Sie diese Konfigurationsseite auf einer separaten Browserregister Karte geöffnet, da Sie Sie während des restlichen Prozesses verwenden werden.

Weitere Informationen dazu, wie Sie Moodle-plugins in der Moodle- [Dokumentation](https://docs.moodle.org/34/en/Installing_plugins)installieren können, finden Sie hier.

**Wichtiger Hinweis:** Lassen Sie Ihre Microsoft 365-oder Office 365-Konfigurationsseite für das Moodle-Plugin auf einem separaten Browser-Reiter geöffnet, da Sie während dieses Vorgangs zu dieser Gruppe von Seiten zurückkehren werden.

*Sie haben noch keine Moodle-Website?* Vielleicht möchten Sie unser Moodle auf Azure [Repo](https://github.com/azure/moodle) lesen, in dem Sie eine Moodle-Instanz auf Azure schnell bereitstellen und an Ihre Anforderungen anpassen können.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Schritt 2: Konfigurieren der Verbindung zwischen dem Microsoft 365-oder Office 365-Plug-in und Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Als nächstes müssen Sie Moodle als Anwendung in Ihrem Azure Active Directory registrieren. Wir haben ein PowerShell-Skript bereitgestellt, mit dem Sie diesen Vorgang durchführen können. Das PowerShell-Skript stellt eine neue Azure AD-Anwendung für Ihre Microsoft 365-oder Office 365-Organisation zur Verfügung, die vom Moodle-Plug-in verwendet wird. Das Skript stellt die APP für Ihren Microsoft 365-oder Office 365-Mandanten bereit, richtet alle erforderlichen Antwort-URLs und-Berechtigungen für die bereitgestellte App ein und gibt die Anwendungs-und Schlüsselkennung zurück. Sie können die generierte Anwendungskennung und den Schlüssel auf der Setup Seite ihres Moodle-Plugins verwenden, um Ihren Moodle-Server mit Azure AD zu konfigurieren. Wenn Sie die detaillierten manuellen Schritte anzeigen möchten, die das PowerShell-Skript automatisiert, finden Sie diese in der vollständigen [Dokumentation für das Plug](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)-in.

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Registerkarte "Moodle" für Microsoft Teams-Informationsfluss

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Abbildung der Registerkarte "Moodle" für Microsoft Teams-Informationsfluss" />

1. Wählen Sie auf der Seite Microsoft 365 oder Office 365 Integration Plugin die Registerkarte **Setup** aus.
1. Klicken Sie auf die Schaltfläche **PowerShell-Skript herunterladen** , und speichern Sie Sie auf Ihrem lokalen Computer.
1. Sie müssen das PowerShell-Skript aus der ZIP-Datei vorbereiten. Gehen Sie hierfür wie folgt vor:
    * Laden Sie die Datei herunter, und extrahieren Sie Sie `Moodle-AzureAD-Powershell.zip` .
    * Öffnen Sie den extrahierten Ordner.
    * Klicken Sie mit der rechten Maustaste auf die `Moodle-AzureAD-Script.ps1` Datei, und wählen Sie **Eigenschaften**aus.
    * Aktivieren Sie im Eigenschaftenfenster auf der Registerkarte **Allgemein** das Kontroll `Unblock` Kästchen neben dem **Sicherheits** Attribut unten.
    * Klicken Sie auf **OK**.
    * Kopieren Sie den Verzeichnispfad des extrahierten Ordners.
1. Als nächstes führen Sie PowerShell als Administrator aus:
    * Klicken Sie auf Start.
    * Geben Sie PowerShell ein.
    * Klicken Sie mit der rechten Maustaste auf Windows PowerShell.
    * Klicken Sie auf "als Administrator ausführen".
1. Navigieren Sie zum entzippten Verzeichnis, indem Sie `cd ...\...\Moodle-AzureAD-Powershell` `...\...` den Pfad zum Verzeichnis eingeben.
1. Führen Sie das PowerShell-Skript wie folgt aus:
    * Geben Sie `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` .
    * Geben Sie `.\Moodle-AzureAD-Script.ps1` .
    * Melden Sie sich im Popupfenster bei Ihrem Microsoft 365-oder Office 365-Administrator Konto an.
    * Geben Sie den Namen der Azure AD-Anwendung ein (z. b. Moodle/Moodle-Plugin).
    * Geben Sie die URL Ihres Moodle-Servers ein.
    * Kopieren Sie die **Anwendungs-ID** und den **Anwendungsschlüssel** , die vom Skript generiert wurden, und speichern Sie Sie.
1. Als nächstes müssen Sie die ID und den Schlüssel zum Moodle-Plug-in hinzufügen. Kehren Sie zur Seite Plugin-Verwaltung zurück (Websiteverwaltung > Plugins > Microsoft 365-Integration).
1. Fügen Sie auf der Registerkarte **Setup** die zuvor kopierte **Anwendungs-ID** und den **Anwendungsschlüssel** hinzu, und klicken Sie dann auf **Änderungen speichern**.
1. Sobald die Seite aktualisiert wird, sollten Sie nun einen neuen Abschnitt **"Verbindungsmethode auswählen"** sehen. Klicken Sie auf das Kontrollkästchen **Standard** , und klicken Sie dann erneut auf **Änderungen speichern** .
1. Sobald die Seite aktualisiert wird, sehen Sie eine weitere neue Abschnitts **Administrator Zustimmung & zusätzliche Informationen**.
    * Klicken Sie auf den Link **Administrator Zustimmung bereitstellen** , geben Sie Ihre Microsoft 365-oder Office 365-globalen Administrator Anmeldeinformationen ein, und **akzeptieren** Sie dann, um die Berechtigungen zu erteilen.
    * Klicken Sie neben dem Feld **Azure AD-Mandant** auf die Schaltfläche **erkennen** .
    * Klicken Sie neben der **OneDrive for Business-URL** auf die Schaltfläche **erkennen** .
    * Sobald die Felder gefüllt sind, klicken Sie erneut auf die Schaltfläche **Änderungen speichern** .
1. Klicken Sie auf die Schaltfläche **Aktualisieren** , um die Installation zu überprüfen und dann **Änderungen zu speichern**.
1. Als nächstes müssen Sie die Benutzer zwischen Ihrem Moodle-Server und Azure Active Directory synchronisieren. Je nach Umgebung können Sie in dieser Phase unterschiedliche Optionen auswählen. Beachten Sie, dass die hier festgelegte Konfiguration mit jedem Moodle-cron-Run (in der Regel einmal täglich) ausgeführt wird, um alles synchron zu halten. Erste Schritte:
    * Wechseln zur **Registerkarte "Synchronisierungseinstellungen"**
    * Aktivieren Sie im Abschnitt **Benutzer mit Azure AD synchronisieren** die Kontrollkästchen, die für Ihre Umgebung gelten. In der Regel würden Sie mindestens Folgendes auswählen:
        * Erstellen von Konten in Moodle für Benutzer in Azure AD
        * Aktualisieren aller Konten in Moodle für Benutzer in Azure AD
    * Im Abschnitt **Benutzer Erstellungs Einschränkung** können Sie einen Filter einrichten, um die Azure AD-Benutzer zu begrenzen, die mit Moodle synchronisiert werden.
    * Im Abschnitt **Benutzerfeld Zuordnung** können Sie das Azure AD auf die Benutzerprofilfeld Zuordnung in Moodle anpassen.
    * Im Abschnitt " **Teams-Synchronisierung** " können Sie festlegen, dass Gruppen (also Teams) für einige oder alle Ihrer vorhandenen Moodle-Kurse automatisch erstellt werden.
1. Um die cron-Aufträge zu überprüfen (und diese manuell auszuführen, wenn Sie für den ersten Durchlauf vorgesehen sind) klicken Sie im Abschnitt **Benutzer mit Azure AD synchronisieren** auf den Link **geplante Aufgaben Verwaltungsseite** . Dadurch gelangen Sie zur Seite " **geplante Vorgänge** ".
    * Scrollen Sie nach unten, und suchen Sie den Job **Synchronisieren von Benutzern mit Azure AD** Job, und klicken Sie auf **jetzt ausführen**.
    * Wenn Sie Gruppen basierend auf vorhandenen Kursen erstellen möchten, können Sie auch die Option **Benutzergruppen erstellen in Office 365** -Auftrag ausführen.
1. Kehren Sie zur Seite Plugin-Verwaltung zurück (Websiteverwaltung > Plugins > Microsoft 365-Integration), und wählen Sie die Seite " **Teams-Einstellungen** " aus. Sie müssen einige Sicherheitseinstellungen konfigurieren, um die Integration der Teams-APP zu ermöglichen.
    * Um OpenID Connect zu aktivieren, klicken Sie auf den Link **Authentifizierung verwalten** , und klicken Sie auf das Augensymbol in der **OpenID Connect** -Zeile, wenn es abgeblendet ist.
    * Als nächstes müssen Sie die Frame Einbettung aktivieren. Klicken Sie auf den Link **http-Sicherheit** , und klicken Sie dann auf das Kontrollkästchen neben **Frame Einbettung zulassen**.
    * Der nächste Schritt besteht darin, Webdienste zu aktivieren, die die Moodle-API-Funktionen aktivieren werden. Klicken Sie auf den Link **Erweiterte Funktionen** , und stellen Sie sicher, dass das Kontrollkästchen neben **Webdienste aktivieren** aktiviert ist.
    * Schließlich müssen Sie die externen Dienste für Microsoft 365 oder Office 365 aktiviert haben. Klicken Sie dann auf den Link **externe Dienste** :
        * Klicken Sie in der Zeile **Moodle Office 365 Webservices** auf **Bearbeiten** .
        * Markieren Sie das Kontrollkästchen neben **aktiviert**, und klicken Sie dann auf **Änderungen speichern** .
    * Als nächstes müssen Sie die Berechtigungen für authentifizierte Benutzer bearbeiten, damit diese Webdienst Tokens erstellen können. Klicken Sie auf den Link **"authentifizierter Benutzer" der Rolle "Bearbeiten"** . Scrollen Sie nach unten, und suchen Sie nach der Funktion **Create a Web Service Token** , und markieren Sie das Kontrollkästchen **zulassen** .

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Schritt 3: Bereitstellen des Moodle Assistant-bot in Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Der ﻿kostenlose Moodle Assistant-bot für Microsoft Teams hilft Lehrern und Schülern, Fragen zu ihren Kursen, Aufgaben, Noten und anderen Informationen in Moodle zu beantworten. Der bot sendet auch Moodle-Benachrichtigungen an Schüler und Lehrer direkt in Teams. Dieser Bot ist ein von Microsoft verwaltetes Open-Source-Projekt und steht [auf GitHub zur Verfügung](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> In diesem Abschnitt werden Ressourcen für Ihr Azure-Abonnement bereitgestellt, und alle Ressourcen werden mithilfe der **kostenlosen** Ebene konfiguriert. Je nach Nutzung Ihres bot müssen Sie möglicherweise diese Ressourcen skalieren.
> Wenn Sie einfach den Reiter Moodle ohne bot verwenden möchten, fahren Sie mit [Schritt 4 fort](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Informationsfluss für Moodle-bot

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Abbildung des Moodle-bot für Microsoft Teams-Informationsfluss" />


Um den bot zu installieren, müssen Sie ihn zunächst auf der [Microsoft Identity-Plattform](https://identity.microsoft.com/Landing)registrieren. Dadurch kann sich Ihr bot für Ihre Microsoft-Endpunkte authentifizieren. So registrieren Sie Ihren bot:

1. Kehren Sie zur Seite Plugin-Verwaltung zurück (Websiteverwaltung > Plugins > Microsoft 365-Integration), und wählen Sie die Registerkarte **Einstellungen für Teams** aus.
1. Klicken Sie auf den Link " **Microsoft Application Registration Portal** " und melden Sie sich mit Ihrer Microsoft-ID an.
1. Geben Sie einen Namen für Ihre APP ein (z. b. MoodleBot) und klicken Sie auf die Schaltfläche **Erstellen** .
1. Kopieren Sie die **Anwendungs-ID** , und fügen Sie Sie auf der Seite **Team Einstellungen** in das Feld **bot-Anwendungs-ID** ein.
1. Klicken Sie auf die Schaltfläche **Neues Kennwort generieren** . Kopieren Sie das generierte Kennwort, und fügen Sie es auf der Seite " **Team Einstellungen** " in das Feld " **bot-Anwendungs Kennwort** " ein.
1. Scrollen Sie zum Ende des Formulars, und klicken Sie auf **Änderungen speichern**.

Nachdem Sie Ihre Anwendungs-ID und Ihr Kennwort generiert haben, ist es an der Zeit, ihren bot in Azure bereitzustellen. Klicken Sie auf die Schaltfläche **in Azure bereitstellen** , und füllen Sie das Formular mit den erforderlichen Informationen aus (die bot-Anwendungs-ID, das Kennwort für die bot-Anwendung und das Moodle-Kennwort befinden sich auf der Seite **Teameinstellungen** , und die Azure-Informationen finden Sie auf der Seite **Setup** ). Nachdem Sie das Formular ausgefüllt haben, klicken Sie auf das Kontrollkästchen, um den allgemeinen Geschäftsbedingungen zuzustimmen, und klicken Sie dann auf die Schaltfläche " **kaufen** " (alle Azure-Ressourcen werden auf der kostenlosen Ebene bereitgestellt).

Nachdem die Ressourcen in Azure bereitgestellt wurden, müssen Sie das Moodle-Plug-in mit dem Messaging Endpunkt konfigurieren. Zunächst müssen Sie den Endpunkt aus Ihrem bot in Azure abrufen. Gehen Sie dazu wie folgt vor:

1. Wenn Sie noch nicht angemeldet sind, melden Sie sich beim [Azure-Portal](https://portal.azure.com)an.
2. Wählen Sie im linken Bereich **Ressourcengruppen**aus.
3. Wählen Sie in der Liste die Ressourcengruppe aus, die Sie gerade verwendet (oder erstellt) haben, während Sie Ihren bot bereitstellen.
4. Wählen Sie in der Liste der Ressourcen in der Gruppe die Ressource für den Webressourcen- **bot** aus.
5. Kopieren Sie den **Nachrichten Endpunkt** aus dem Abschnitt **Übersicht** .
6. Öffnen Sie in Moodle die Seite **Team Einstellungen** ihres Moodle-Plugins.
7. Fügen Sie im Feld **bot-Endpunkt** die URL ein, die Sie soeben kopiert haben, und ändern Sie die Word- *Nachrichten* in *webhook*. Die URL sollte nun wie folgt aussehen`https://botname.azurewebsites.net/api/webhook`
8. Klicken Sie auf **Änderungen speichern** .
9. Nachdem Sie Ihre Änderungen gespeichert haben, wechseln Sie zurück zur Registerkarte **Team Einstellungen** , klicken Sie auf die Schaltfläche **Manifestdatei herunterladen** , und speichern Sie das Manifest-Paket auf dem Computer (im nächsten Abschnitt verwenden Sie es).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Schritt 4: Bereitstellen Ihrer Microsoft Teams-App

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Nachdem Sie Ihren bot in Azure bereitgestellt und für die Kommunikation mit Ihrem Moodle-Server konfiguriert haben, ist es an der Zeit, Ihre Microsoft Teams-App bereitzustellen. Zu diesem Zweck laden Sie die Manifestdatei, die Sie aus der Seite Moodle Plugin Team Settings heruntergeladen haben, im vorherigen Schritt.

Bevor Sie die APP installieren können, müssen Sie sicherstellen, dass externe apps und Sideloading von apps aktiviert sind. Führen Sie dazu die [folgenden Schritte aus](https://docs.microsoft.com/MicrosoftTeams/admin-settings). Nachdem Sie sichergestellt haben, dass externe apps aktiviert sind, können Sie die folgenden Schritte ausführen, um Ihre APP bereitzustellen.

1. Öffnen Sie Microsoft Teams.
2. Klicken Sie auf das **Store** -Symbol in der unteren linken Ecke der Navigationsleiste.
3. Klicken Sie in der Liste der Optionen auf den Link **benutzerdefinierte App hochladen** . *Hinweis:* Wenn Sie als globaler Administrator angemeldet sind, haben Sie die Möglichkeit, die app in den App Store Ihrer Organisation hochzuladen, da Sie andernfalls nur die APP für Teams laden können, an denen Sie teilnehmen ("Sideloading").
4. Wählen Sie das `manifest.zip` Paket, das Sie zuvor heruntergeladen haben, und klicken Sie auf **Speichern**. Wenn Sie das Manifest-Paket noch nicht heruntergeladen haben, können Sie dies über die Registerkarte " **Team Einstellungen** " auf der Seite "Plugin-Konfiguration" in Moodle tun.

Nachdem Sie die APP installiert haben, können Sie die Registerkarte jedem Kanal hinzufügen, auf den Sie Zugriff haben. Navigieren Sie dazu zum Kanal, klicken Sie auf das **+** Symbol, und wählen Sie Ihre APP in der Liste aus. Folgen Sie den Anweisungen, um das Hinzufügen Ihrer Moodle-Kurs Registerkarte zu einem Kanal abzuschließen.

Das wars! Sie und Ihr Team können nun mit ihren Moodle-Kursen direkt von Microsoft Teams aus arbeiten.

Wenn Sie Fragen oder Feedback zu anderen Funktionen an uns weitergeben möchten, besuchen Sie bitte unsere [Nutzer-Sprachseite](https://microsoftteams.uservoice.com/forums/916759-moodle).
