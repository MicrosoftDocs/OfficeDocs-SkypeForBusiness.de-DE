---
title: Installieren von Moodle-Integration in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Erfahren Sie, wie Sie die Open-Source Learning Management System (LMS)-App Moodle für Microsoft Teams installieren und konfigurieren.
keywords: Plug-In zur Integration der Moodle-App für Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 061978876e9e8c092f19049ca5f44dd81a9b1012
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592301"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Installation der Moodle-Integration in Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), das beliebteste und Open-Source Learning Management System (LMS) der Welt, ist jetzt in Microsoft Teams integriert! Diese Integration hilft Lehrern und Lehrkräften bei der Zusammenarbeit an Moodle-Kursen, bei Fragen zu Noten und Aufgaben und bei der Aktualisierung der Benachrichtigungen – direkt in Microsoft Teams!

Um IT-Administratoren bei der einfachen Einrichtung dieser Integration zu unterstützen, haben wir unser Open-Source-Moodle-Plug-In mit den folgenden Funktionen aktualisiert:

* Automatische Registrierung Ihres Moodle-Servers bei Azure AD.
* Bereitstellung Ihres Moodle Assistant-Bots für Azure mit einem Klick.
* Automatische Bereitstellung von Teams und automatische Synchronisierung der Teamanmeldungen für alle oder ausgewählte Moodle-Kurse.
* Automatische Installation der Moodle-Registerkarte und des Moodle Assistant-Bots in jedem synchronisierten Team. (Bald verfügbar)
* Veröffentlichung der Moodle-App in Ihrem privaten Teams App Store mit einem Klick. (Bald verfügbar)

Weitere Informationen zu den Funktionen, die diese Integration bietet, finden Sie unter [Installieren der Moodle-Integration mit Microsoft Teams.](/microsoftteams/platform/resources/moodleinstructions)

## <a name="prerequisites"></a>Voraussetzungen

Um diese Anwendung installieren und konfigurieren zu können, benötigen Sie:

1. Moodle-Administratoranmeldeinformationen
2. Azure AD-Administratoranmeldeinformationen
3. Ein Azure-Abonnement, in dem Sie neue Ressourcen erstellen können

## <a name="step-1-install-the-moodle-plugin"></a>Schritt 1: Installieren des Moodle-Plug-Ins

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Die Moodle-Integration in Microsoft Teams wird vom Open-Source [Moodle-Plug-In-Set](https://github.com/Microsoft/o365-moodle) unterstützt. So installieren Sie das Plug-In auf Ihrem Moodle-Server:

1. Laden Sie zuerst das [Moodle-Plug-In-Set](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) herunter und speichern Sie es auf Ihrem lokalen Computer. Sie müssen Version 3.5 oder höher verwenden.
    * Wenn Sie das Plug-In local_o365 installieren, werden auch die Plug-Ins [auth_oidc](https://moodle.org/plugins/auth_oidc) und [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) installiert.
1. Melden Sie sich bei Ihrem Moodle-Server als Administrator an, und wählen **Sie** im linken Navigationsbereich Websiteverwaltung aus.
1. Wählen Sie die Registerkarte **Plug-Ins** und klicken Sie dann auf **Plug-Ins installieren**.
1. Klicken Sie unter dem Abschnitt **Plug-In aus ZIP-Datei installieren** auf die Schaltfläche **Datei auswählen**.
1. Wählen Sie **Hochladen linken Navigationsbereich** die Option Datei auswählen aus, suchen Sie nach der oben heruntergeladenen Datei, und klicken Sie **Hochladen datei .**
1. Wählen Sie im linken Navigationsbereich die Option **Websiteverwaltung** erneut aus, um zu Ihrem Administrator-Dashboard zurückzukehren. Scrollen Sie nach unten zu **Lokale Plug-Ins** und klicken Sie auf den Link **Microsoft Office 365-Integration**. Lassen Sie diese Konfigurationsseite in einer separaten Browser-Registerkarte geöffnet, da Sie diese während des gesamten weiteren Verlaufs dieses Vorgangs verwenden werden.

Weitere Informationen über die Installation von Moodle-Plug-Ins finden Sie in der [Moodle-Dokumentation](https://docs.moodle.org/34/en/Installing_plugins).

**Wichtiger Hinweis:** Lassen Sie Ihre Moodle-Plug-In-Konfigurationsseite für Microsoft 365 oder Office 365 in einer separaten Browser-Registerkarte geöffnet, da Sie während des gesamten Vorgangs zu diesen Seiten zurückkehren werden.

*Sie haben noch keine Moodle-Website?* Vielleicht möchten Sie sich unser „Moodle on Azure“-[Repository](https://github.com/azure/moodle) ansehen, wo Sie schnell eine Moodle-Instanz auf Azure einsetzen und an Ihre Bedürfnisse anpassen können.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>Schritt 2: Konfigurieren der Verbindung zwischen dem Microsoft 365- oder Office 365-Plug-In und Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Als nächstes müssen Sie Moodle als Anwendung in Ihrem Azure Active Directory registrieren. Wir haben ein PowerShell-Skript bereitgestellt, das Sie bei diesem Vorgang unterstützt. Das PowerShell-Skript stellt eine neue Azure AD-Anwendung für Ihre Microsoft 365- oder Office 365-Organisation bereit, die vom Moodle-Plug-In verwendet wird. Das Skript stellt die Anwendung für Ihren Microsoft 365- oder Office 365-Mandanten bereit, richtet alle erforderlichen Antwort-URLs und Berechtigungen für die bereitgestellte Anwendung ein und gibt die App-ID und den Schlüssel zurück. Sie können die generierte App-ID und den Schlüssel in der Setup-Seite Ihres Moodle-Plug-Ins verwenden, um Ihren Moodle-Server mit Azure AD zu konfigurieren. Wenn Sie die detaillierten manuellen Schritte sehen möchten, die das PowerShell-Skript automatisiert, finden Sie diese in der vollständigen [ Dokumentation für das Plug-In](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Registerkarte "Moodle" für Microsoft Teams – Informationsfluss

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Abbildung der Registerkarte "Moodle" für Microsoft Teams – Informationsfluss" />

1. Wählen Sie auf der Plug-In-Seite Microsoft 365- oder Office 365-Integration die Registerkarte **Setup** aus.
1. Klicken Sie auf die Schaltfläche **PowerShell-Skript herunterladen** und speichern Sie es auf Ihrem lokalen Computer.
1. Sie müssen das PowerShell-Skript aus der ZIP-Datei vorbereiten. Gehen Sie hierzu folgendermaßen vor:
    * Herunterladen und Extrahieren der Datei `Moodle-AzureAD-Powershell.zip`.
    * Öffnen Sie den extrahierten Ordner.
    * Klicken Sie mit der rechten Maustaste auf die Datei `Moodle-AzureAD-Script.ps1`, und wählen Sie **Eigenschaften** aus.
    * Aktivieren Sie auf der Registerkarte **Allgemein** des Fensters "Eigenschaften" das Kontrollkästchen `Unblock`unten neben dem Attribut **Sicherheit**.
    * Klicken Sie auf **OK**.
    * Kopieren Sie den Verzeichnispfad des extrahierten Ordners.
1. Als nächstes führen Sie PowerShell als Administrator aus:
    * Klicken Sie auf "Start".
    * Geben Sie PowerShell ein.
    * Klicken Sie mit der rechten Maustaste auf Windows PowerShell.
    * Klicken Sie auf "Als Administrator ausführen".
1. Navigieren Sie zu dem nicht gezippten Verzeichnis, indem Sie `cd ...\...\Moodle-AzureAD-Powershell` eingeben, wobei `...\...` der Pfad zum Verzeichnis ist.
1. Ausführen des PowerShell-Skripts nach:
    * Geben Sie `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` ein.
    * Geben Sie `.\Moodle-AzureAD-Script.ps1` ein.
    * Melden Sie sich im Popup-Fenster bei Ihrem Microsoft 365- oder Office 365-Administratorkonto an.
    * Geben Sie den Namen der Azure AD-Anwendung ein (z. B. Moodle/Moodle-Plug-In).
    * Geben Sie die URL Ihres Moodle-Servers ein.
    * Kopieren Sie die vom Skript generierte **Anwendungs-ID** und den **Anwendungsschlüssel** und speichern Sie diese.
1. Als nächstes müssen Sie die ID und den Schlüssel zum Moodle-Plug-In hinzufügen. Kehren Sie zur Plug-In-Verwaltungsseite zurück (Websiteverwaltung > Plug-Ins > Microsoft 365-Integration).
1. Fügen Sie auf der Registerkarte **Setup** die **Anwendungs-ID** und den **Anwendungsschlüssel** hinzu, die Sie zuvor kopiert haben, und klicken Sie dann auf **Änderungen speichern**.
1. Sobald die Seite aktualisiert wird, sollten Sie nun einen neuen Abschnitt **Verbindungsmethode wählen** sehen. Klicken Sie auf das Kontrollkästchen mit der Bezeichnung **Standard** und dann erneut auf **Änderungen speichern**.
1. Sobald die Seite aktualisiert wird, sehen Sie einen weiteren neuen Abschnitt **Administratorzustimmung und weitere Informationen**.
    * Klicken Sie auf den Link **Administratorzustimmung erteilen**, geben Sie Ihre Anmeldeinformationen als globaler Microsoft 365- oder Office 365-Administrator ein und klicken Sie dann auf **Annehmen**, um die Berechtigungen zu erteilen.
    * Klicken Sie neben dem Feld **Azure AD-Mandanten** auf die Schaltfläche **Erkennen**.
    * Klicken Sie neben der URL **OneDrive for Business** auf die Schaltfläche **Erkennen**.
    * Sobald die Felder aufgefüllt sind, klicken Sie erneut auf die Schaltfläche **Änderungen speichern**.
1. Klicken Sie auf die Schaltfläche **Aktualisieren**, um die Installation zu überprüfen, und dann auf **Änderungen speichern**.
1. Als nächstes müssen Sie die Benutzer zwischen Ihrem Moodle-Server und Azure Active Directory synchronisieren. Je nach Umgebung können Sie in dieser Phase unterschiedliche Optionen auswählen. Beachten Sie, dass die Konfiguration, die Sie hier einstellen, bei jedem Moodle-CRON-Durchlauf (in der Regel einmal am Tag) ausgeführt wird, um alles synchron zu halten. Erste Schritte:
    * Wechseln Sie zur Registerkarte **Einstellungen synchronisieren**
    * Aktivieren Sie im Abschnitt **Benutzer mit Azure AD synchronisieren** die Kontrollkästchen, die für Ihre Umgebung gelten. In der Regel würden Sie mindestens Folgendes auswählen:
        * Erstellen von Konten in Moodle für Benutzer in Azure AD
        * Aktualisieren aller Konten in Moodle für Benutzer in Azure AD
    * Im Abschnitt **Benutzererstellungseinschränkung** können Sie einen Filter einrichten, um die Azure AD-Benutzer zu beschränken, die mit Moodle synchronisiert werden.
    * Im Abschnitt **Benutzer-Feldzuordnung** können Sie Azure AD auf die Benutzerprofil-Feldzuordnung von Moodle anpassen.
    * Im Abschnitt **Teams synchronisieren** können Sie festlegen, dass Gruppen (d. h. Teams) für einige oder alle der vorhandenen Moodle-Kurse automatisch erstellt werden.
1. Um die CRON-Aufträge zu validieren (und sie manuell auszuführen, wenn Sie dies für den ersten Durchlauf wünschen), klicken Sie auf den Link **Verwaltungsseite für geplante Aufgaben** im Abschnitt **Benutzer mit Azure AD synchronisieren**. Dadurch gelangen Sie zur Seite **Geplante Aufgaben**.
    * Scrollen Sie nach unten und suchen Sie den Auftrag **Benutzer mit Azure AD synchronisieren** und klicken Sie auf **Jetzt ausführen**.
    * Wenn Sie sich dafür entschieden haben, Gruppen auf der Grundlage bestehender Kurse zu erstellen, können Sie auch den Auftrag **Benutzergruppen in Office 365 erstellen** ausführen.
1. Kehren Sie zur Plug-In-Verwaltungsseite zurück (Websiteverwaltung > Plug-Ins > Microsoft 365-Integration) und wählen Sie die Seite **Teams-Einstellungen** aus. Sie müssen einige Sicherheitseinstellungen konfigurieren, um die Integration der Teams-App zu ermöglichen.
    * Um "OpenID Connect" zu aktivieren, klicken Sie auf den Link **Authentifizierung verwalten** und klicken Sie auf das Augensymbol in der Zeile **OpenId Connect**, wenn es abgeblendet ist.
    * Als nächstes müssen Sie die Frame-Einbettung aktivieren. Klicken Sie auf den Link **HTTP-Sicherheit** und dann auf das Kontrollkästchen neben **Frame-Einbettung zulassen**.
    * Der nächste Schritt besteht darin, Webdienste zu aktivieren, welche die Features der Moodle-API aktivieren. Klicken Sie auf den Link **Erweiterte Features**, und stellen Sie sicher, dass das Kontrollkästchen neben **Webdienste aktivieren** aktiviert ist.
    * Schließlich müssen Sie die externen Dienste für ihre Microsoft 365 oder Office 365. Klicken Sie auf den Link **Externe Dienste**, und dann:
        * Klicken Sie auf **Bearbeiten** in der Zeile **Moodle Office 365-Webdienste**.
        * Aktivieren Sie das Kontrollkästchen neben **Aktiviert**, und klicken Sie dann auf **Änderungen speichern**
    * Als nächstes müssen Sie die Berechtigungen für authentifizierte Benutzer bearbeiten, damit Sie Webdienst-Token erstellen können. Klicken Sie auf den Link **Bearbeitungsrolle "Authentifizierter Benutzer"**. Scrollen Sie nach unten und suchen Sie die Funktion **Webdienst-Token erstellen** und aktivieren Sie das Kontrollkästchen **Zulassen**.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Schritt 3: Bereitstellen des Moodle Assistant-Bots für Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Der kostenlose Moodle Assistant-Bot für Microsoft Teams hilft Lehrkräften und Schülern, Fragen zu ihren Kursen, Aufgaben, Noten und anderen Informationen in Moodle zu beantworten. Der Bot sendet außerdem direkt innerhalb der Teams Moodle-Benachrichtigungen an Schüler und Lehrkräfte. Bei diesem Bot handelt es sich um ein Open-Source-Projekt, das von Microsoft verwaltet wird und auf [GitHub verfügbar](https://github.com/microsoft/Moodle-Teams-Bot) ist.

> [!NOTE]
> In diesem Abschnitt werden Sie Ressourcen für Ihr Azure-Abonnement bereitstellen, und alle Ressourcen werden unter Verwendung von **Free**-Tarif konfiguriert. Je nach der Nutzung Ihres Bots müssen Sie diese Ressourcen möglicherweise skalieren.
> Wenn Sie die Registerkarte "Moodle" nur ohne den Bot verwenden möchten, wechseln Sie zu [Schritt 4](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Moodle-Bot – Informationsfluss

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Abbildung des Moodle-Bots für Microsoft Teams – Informationsfluss" />


Um den Bot zu installieren, müssen Sie ihn zuerst auf der [Microsoft Identity Platform](https://identity.microsoft.com/Landing) registrieren. Auf diese Weise kann Ihr Bot sich gegen Ihre Microsoft-Endpunkte authentifizieren. So registrieren Sie den Bot:

1. Kehren Sie zur Seite "Administrator" (Websiteverwaltung > Plug-Ins > Microsoft 365-Integration) zurück, und wählen Sie die Registerkarte **Teams-Einstellungen** aus.
1. Klicken Sie auf den Link **Registrierungsportal für Microsoft-Anwendungen** und melden Sie sich mit Ihrer Microsoft-ID an.
1. Geben Sie einen Namen für Ihre App ein (z. B. MoodleBot), und klicken Sie auf die Schaltfläche **Erstellen**.
1. Kopieren Sie die **Anwendungs-ID**, und fügen Sie diese in das Feld **Bot-Anwendungs-ID** auf der Seite **Teams-Einstellungen** ein.
1. Klicken Sie auf die Schaltfläche **Neues Kennwort generieren**. Kopieren Sie das generierte Kennwort, und fügen Sie es in das Feld **"Bot Application Password"** auf der **Teamseite Einstellungen** ein.
1. Scrollen Sie zum Ende des Formulars, und klicken Sie auf **Änderungen speichern**.

Nachdem Sie Ihre Anwendungs-ID und das Kennwort generiert haben, ist es an der Zeit, den Bot in Azure bereitzustellen. Klicken Sie auf die Schaltfläche **Auf Azure bereitstellen** und füllen Sie das Formular mit den notwendigen Informationen aus (die Bot-Anwendungs-ID, das Bot-Anwendungs-Kennwort und das Moodle Secret befinden sich auf der Seite **Teams-Einstellungen**, und die Azure-Informationen befinden sich auf der Seite **Setup**). Sobald Sie das Formular ausgefüllt haben, klicken Sie auf das Kontrollkästchen, um den Bedingungen zuzustimmen, und klicken Sie dann auf die Schaltfläche **Kaufen** (alle Azure-Ressourcen werden auf den Free-Tarif bereitgestellt).

Nachdem die Bereitstellung der Ressourcen in Azure abgeschlossen ist, müssen Sie das Moodle-Plug-In mit seinem Nachrichtenendpunkt konfigurieren. Zuerst müssen Sie den Endpunkt aus Ihrem Bot in Azure abrufen. Gehen Sie dazu wie folgt vor:

1. Wenn Sie noch nicht angemeldet sind, melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Wählen Sie im linken Bereich **Ressourcengruppen** aus.
3. Wählen Sie aus der Liste die Ressourcengruppe aus, die Sie während der Bereitstellung Ihres Bot gerade verwendet (oder erstellt) haben.
4. Wählen Sie die Ressource **WebApp-Bot** aus der Liste der Ressourcen in der Gruppe aus.
5. Kopieren Sie den **Messaging-Endpunkt** aus dem Abschnitt **Übersicht**.
6. Öffnen Sie in Moodle die Seite **Teams-Einstellungen** Ihres Moodle-Plug-Ins.
7. Fügen Sie in das Feld **Bot-Endpunkt** die URL ein, die Sie gerade kopiert haben, und ändern Sie das Wort *Nachrichten* in *Webhook*. Die URL sollte nun wie folgt aussehen `https://botname.azurewebsites.net/api/webhook`
8. Klicken Sie auf **Änderungen speichern**
9. Sobald Sie Ihre Änderungen gespeichert haben, gehen Sie zurück zur Registerkarte **Teams-Einstellungen**, klicken Sie auf die Schaltfläche **Manifestdatei herunterladen** und speichern Sie das Manifestpaket auf Ihrem Computer (Sie werden es im nächsten Abschnitt verwenden).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Schritt 4: Bereitstellen Ihrer Microsoft Teams-App

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Nachdem Sie Ihren Bot bei Azure bereitgestellt und so konfiguriert haben, dass er mit Ihrem Moodle-Server kommuniziert, ist es an der Zeit, Ihre Microsoft Teams-App bereitzustellen. Dazu laden Sie die Manifestdatei, die Sie im vorherigen Schritt von der Seite "Teams-Einstellungen" des Moodle-Plug-Ins heruntergeladen haben.

Bevor Sie die App installieren können, müssen Sie sicherstellen, dass externe Apps und das Querladen von Apps aktiviert ist. Dazu können Sie [diese Schritte](./admin-settings.md) ausführen. Nachdem Sie sichergestellt haben, dass externe Apps aktiviert sind, können Sie die folgenden Schritte ausführen, um die App bereitzustellen.

1. Öffnen Sie Microsoft Teams.
2. Klicken Sie **Store** Symbol "Schaltflächensymbol" unten links auf der Navigationsleiste.
3. Klicken Sie in der Liste der Optionen auf den Link **Benutzerdefinierte App hochladen**. *Hinweis:* Wenn Sie als globaler Administrator angemeldet sind, haben Sie die Möglichkeit, die App in den App-Store Ihrer Organisation hochzuladen. Andernfalls können Sie die App nur für Teams laden, zu denen Sie gehören ("Querladen").
4. Wählen Sie das `manifest.zip`-Paket aus, das Sie zuvor heruntergeladen haben, und klicken Sie auf **Speichern**. Falls Sie das Manifest-Paket noch nicht heruntergeladen haben, können Sie dies über die Registerkarte **Teams-Einstellungen** der Konfigurationsseite des Plug-Ins in Moodle tun.

Nachdem Sie die App installiert haben, können Sie die Registerkarte zu jedem Kanal hinzufügen, auf den Sie Zugriff haben. Navigieren Sie dazu zum Kanal, klicken Sie auf das Symbol **+** und wählen Sie Ihre Anwendung aus der Liste aus. Folgen Sie den Eingabeaufforderungen, um das Hinzufügen Ihrer Registerkarte "Moodle-Kurs" zu einem Kanal abzuschließen.

Das ist alles. Jetzt können Sie und Ihr Team direkt von Microsoft Teams aus mit Ihren Moodle-Kursen arbeiten.

Wenn Sie uns Vorschläge für neue Features oder Feedback mitteilen möchten, besuchen Sie bitte unsere Seite [User Voice](https://microsoftteams.uservoice.com/forums/916759-moodle).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]