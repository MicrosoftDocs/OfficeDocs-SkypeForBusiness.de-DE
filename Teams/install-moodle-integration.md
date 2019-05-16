---
title: Installieren von Moodle Integration mit Microsoft-Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 05/01/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Informationen Sie zum Installieren und konfigurieren die Moodle Integration app für Microsoft-Teams.
keywords: Teams Moodle app Integration-Plug-Ins
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto: Microsoft Teams
ms.openlocfilehash: 92259a9ef01232aaeca67089b5d654fe302f1224
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "34055365"
---
# <a name="install-moodle-integration-with-microsoft-teams"></a>Installieren von Moodle Integration mit Microsoft-Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/), die am häufigsten beliebte und open-Source Learning Management System (LMS) in der ganzen Welt ist nun mit Microsoft-Teams integriert! Diese Integration erleichtert die Lehrer und Lehrer zusammenarbeiten können Moodle Kurse, Fragen Sie ihren Klassen und Zuordnungen und informieren Sie sich mit Benachrichtigungen – alles innerhalb Teams!

Damit IT-Administratoren auf einfache Weise diese Integration einrichten gewährleistet ist, haben wir unsere open-Source-Plug-in Office 365 Moodle mit den folgenden Funktionen aktualisiert:

- Automatische Registrierung Ihres Servers Moodle mit Azure AD
- Bereitstellung des Ihrer Bot Moodle-Assistent für Azure per Mausklick
- Automatische Bereitstellung von Teams und der Registrierung für alle für die Team, oder wählen Sie Moodle Kurse Auto-Synchronisierung
- Automatische Installation der Registerkarte Moodle und den Robot Moodle-Assistent in jedes synchronisierte Team (bald verfügbar)
- Per Mausklick Veröffentlichen der app Moodle in Ihre private Teams App-Store (bald verfügbar)

## <a name="prerequisites"></a>Voraussetzungen

So installieren und Konfigurieren dieser Anwendung, die Sie benötigen:

- Moodle Administratoranmeldeinformationen
- Azure AD-Administratoranmeldeinformationen
- Ein Azure-Abonnement, das Sie in neue Ressourcen erstellen können

## <a name="step-1-install-the-office-365-moodle-plugin"></a>Schritt 1: Installieren der Office 365 Moodle-Plug-in

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Die Moodle Integration in Microsoft-Teams, wird durch die open-Source [-Plug-in Office 365 Moodle](https://github.com/Microsoft/o365-moodle)betrieben werden. So installieren Sie das Plug-in auf Ihrem Server Moodle:

1. Herunterladen Sie das [Festlegen von Office 365-Plug-in](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) und speichern Sie sie auf dem lokalen Computer. Sie müssen die Version 3.5 oder höher verwenden.
2. Melden Sie sich bei Ihrem Moodle Server als Administrator, und wählen Sie **die Verwaltung von** im linken Navigationsbereich.
3. Wählen Sie die Registerkarte **-Plug-Ins** , und klicken Sie dann auf **-Plug-Ins zu installieren**.
4. Klicken Sie auf **Wählen Sie eine Datei** , klicken Sie im Abschnitt **aus ZIP-Datei-Plug-in installieren** .
5. Wählen Sie die Optionen zum **Hochladen einer Datei** im linken Navigationsbereich, navigieren Sie zu der Datei, der Sie über heruntergeladen haben, und klicken Sie auf **Diese Datei hochladen**.
6. Wählen Sie die Option **Site-Verwaltung** aus im linken Navigationsbereich, um zum Dashboard Admin zurückzukehren. Führen Sie einen Bildlauf nach unten zu den **lokalen-Plug-Ins** , und klicken Sie auf den Link für die **Integration in Microsoft Office 365** . Lassen Sie diese Konfigurationsseite in einer gesonderten Browserfenster Registerkarte geöffnet: Sie werden verwenden sie den Rest dieses Vorgangs.

Sie können weitere Informationen zum Installieren von Moodle-Plug-Ins in der [Dokumentation zu Moodle](https://docs.moodle.org/34/en/Installing_plugins)finden.

> [!IMPORTANT]
> Lassen Sie Ihre Office 365 Moodle-Plug-in-Konfigurationsseite in einem separaten Browserfenster Registerkarte geöffnet: werden in diesem Satz von Seiten während dieses Prozesses zurückgegeben werden.

Sie haben eine Website Moodle bereits nicht? Möglicherweise möchten unsere Moodle auf Azure [Repo](https://github.com/azure/moodle) Auschecken, können Sie schnell eine Moodle-Instanz auf Azure bereitgestellt wird, und es auf Ihre Bedürfnisse anpassen.

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>Schritt 2: Konfigurieren Sie die Verbindung zwischen dem Office 365-Plug-in und Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

Als Nächstes müssen Sie als eine Anwendung im Azure Active Directory (AD Azure) Moodle registrieren. Wir haben ein PowerShell-Skript, mit denen Sie das folgende Verfahren durchführen bereitgestellt. PowerShell-Skript bereitgestellt wird, eine neue Azure AD-Anwendung für Ihre Office 365-Mandanten, von der Office 365 Moodle-Plug-in verwendet werden soll. Das Skript wird die app für Ihre Office 365-Mandanten bereitstellen, richten Sie alle erforderlichen Antwort URLs und Berechtigungen für die bereitgestellten app und die AppID und Schlüssel zurück. Generierte AppID und Schlüssel können auf der Setupseite-Moodle O365-Plug-in Sie um den Server Moodle mit Azure AD zu konfigurieren. Wenn Sie die manuelle Schritte im Detail angezeigt, die das PowerShell-Skript automatisieren ist möchten, finden Sie diese in die vollständige [Dokumentation für das Plug-in](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

1. Wählen Sie auf der Seite Integration in Microsoft Office 365-Plug-in der Registerkarte **Setup** .
2. Klicken Sie auf die Schaltfläche **Herunterladen PowerShell-Skript** , und speichern Sie das Skript auf dem lokalen Computer.
3. Sie müssen das PowerShell-Skript aus der ZIP-Datei vorbereiten. Gehen Sie dazu so vor:
    1. Herunterladen Sie und extrahieren Sie die Datei Moodle-AzureAD-Powershell.zip.
    2. Öffnen Sie den extrahierten Ordner.
    3. Mit der rechten Maustaste der Moodle-AzureAD-Script.ps1-Datei, und wählen Sie **Eigenschaften**aus.
    4. Klicken Sie auf der Registerkarte **Allgemein** des Fensters Eigenschaften das Kontrollkästchen Sie **Zulassen** neben dem Attribut **Sicherheit** , klicken Sie unten.
    5. Klicken Sie auf **OK**.
    6. Kopieren Sie den Verzeichnispfad des extrahierten Ordners.
4. Als Nächstes müssen Sie PowerShell als Administrator ausführen:
    1. Klicken Sie auf Start.
    2. Typ **PowerShell**.
    3. Mit der rechten Maustaste in der **Windows PowerShell**.
    4. Klicken Sie auf **als Administrator ausführen**.
5. Navigieren Sie zum Verzeichnis entzippten durch Eingabe `cd ...\...\Moodle-AzureAD-Powershell` , in dem `...\...` ist der Pfad zu dem Verzeichnis.
6. Führen Sie das PowerShell-Skript:
    1. Geben Sie `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    2. Geben Sie `.\Moodle-AzureAD-Script.ps1`.
    3. Melden Sie sich bei Ihrem Office 365-Administratorkonto im Popupfenster.
    4. Geben Sie den Namen der Azure AD-Anwendung (z. B. **Moodle/Moodle-Plug-Ins**).
    5. Geben Sie die URL des Servers Moodle.
    6. Kopieren Sie die **ID der Anwendung** und die **Anwendungsschlüssel** generiert, von dem Skript, und speichern Sie sie.
7. Als Nächstes müssen Sie die ID und Key-Plug-in der Office 365 Moodle hinzuzufügen. Zurück zu der Verwaltungsseite der-Plug-in (**websiteverwaltung** > **-Plug-Ins** > **Integration in Microsoft Office 365**).
8. Klicken Sie auf der Registerkarte **Setup** fügen Sie die **ID der Anwendung** und die **Anwendungsschlüssel** , die Sie zuvor kopiert haben, und klicken Sie dann auf **Speichern**.
9. Einmal die Seite wird aktualisiert, sollten Sie einen neuen Abschnitt **Choose Connection-Methode**aufgerufen sehen. Klicken Sie auf das Kontrollkästchen **Standard**, und klicken Sie dann auf **Speichern**.
10. Die Seite wird aktualisiert, wird einmal einen neuen Abschnitt aufgerufen **Admin stimmen & zusätzliche Informationen**angezeigt.
    1. Klicken Sie auf den Link **Bieten Admin stimmen** , geben Sie Ihre Anmeldeinformationen Offices3 365 globaler Administrator, und klicken Sie dann auf **annehmen** , um die Berechtigungen erteilen.
    2. Klicken Sie neben dem Feld **Azure AD-Mandanten** auf die Schaltfläche **erkennen** .
    3. Klicken Sie neben **OneDrive for Business-URL**auf die Schaltfläche **erkennen** .
    4. Nachdem die Felder aufzufüllen, klicken Sie auf die Schaltfläche **Speichern** .
11. Klicken Sie auf die Schaltfläche **Aktualisieren** , um die Installation zu überprüfen, und klicken Sie dann auf **Speichern**.
12. Als Nächstes müssen Sie Benutzer zwischen Moodle Server- und Azure Active Directory zu synchronisieren. Je nach Ihrer Umgebung können Sie verschiedene Optionen während dieser Phase auswählen. Beachten Sie, dass die hier angegebenen Konfiguration mit jedem Moodle Cron (normalerweise einmal täglich) ausführen, um alles synchron zu halten ausgeführt wird. Erste Schritte:
    1. Wechseln Sie zur **Registerkarte Sync-Einstellungen**.
    2. Wählen Sie im Abschnitt **Benutzer mit Azure AD synchronisieren** die entsprechenden Kontrollkästchen, die in Ihrer Umgebung gültigen. In der Regel würden Sie mindestens auswählen:
        - **Erstellen von Konten in Moodle für Benutzer in Azure AD**
        - **Aktualisieren Sie alle Konten im Moodle für Benutzer in Azure AD**
    3. Klicken Sie im Abschnitt **Einschränkung für Benutzer erstellen** können Sie einen Filter festlegen, um die Azure AD-Benutzer zu begrenzen, die mit Moodle synchronisiert werden soll.
    4. Im Abschnitt **Zuordnung zwischen Feld** können Sie zum Anpassen von Azure AD Moodle Benutzerprofil Feld Zuordnung.
    5. Im Abschnitt **Teams synchronisieren** können Sie zum automatischen Erstellen von Gruppen (d. h., Teams) für einige oder alle Ihre vorhandenen Moodle Kurse.
13. Zum Überprüfen der Cron Aufträge (und diese manuell ausführen, wenn Sie für den ersten Textlauf möchten), klicken Sie auf der **Verwaltungsseite für geplante Tasks** im Abschnitt **Benutzer mit Azure AD synchronisieren** . Dadurch gelangen Sie zur Seite **Geplante Tasks** .
    1. Einen Bildlauf nach unten, und wählen Sie den Auftrag **Synchronisieren von Benutzern mit Azure AD** -Auftrag, und klicken Sie auf **jetzt ausführen**.
    2. Wenn Sie Gruppen basierend auf vorhandenen Kurse erstellen möchten, können Sie auch das **Erstellen von Benutzergruppen in Office 365** -Projekt ausführen.
14. Zurück zu der Verwaltungsseite der-Plug-in (**websiteverwaltung** > **-Plug-Ins** > **Integration in Microsoft Office 365**), und wählen Sie die Seite **Einstellungen für Teams** . Sie müssen einige Sicherheitseinstellungen zum Aktivieren der Integration von Teams app zu konfigurieren.
    1. Um OpenID verbinden zu aktivieren, klicken Sie auf den Link für die **Authentifizierung verwalten** , und klicken Sie auf das Augensymbol in der Zeile **OpenId verbinden** , wenn es abgeblendet angezeigt wird.
    2. Um Einbetten von Frame zu aktivieren, klicken Sie auf den Link **Http-Sicherheit** , und wählen Sie dann das Kontrollkästchen neben **Zulassen Frame einbetten**.
    3. Aktivieren von Webdiensten (die den Moodle API-Features aktiviert werden). Klicken Sie auf den Link **Erweiterte Funktionen** , und stellen Sie sicher, dass das Kontrollkästchen neben **Webdienste aktivieren** ausgewählt ist.
    4. Aktivieren Sie die externe Dienste für Office 365. Klicken Sie auf den Link für **externe Dienste** , und klicken Sie dann:
        1. Klicken Sie auf die Zeile **Moodle Office 365 Webservices** **Bearbeiten** .
        2. Aktivieren Sie das Kontrollkästchen neben **aktiviert**, und klicken Sie dann auf **Speichern**
    5. Schließlich müssen Sie Ihre Berechtigungen für authentifizierte Benutzer, dass Benutzer Web Service Token erstellen können bearbeiten. Klicken Sie auf den Link **Bearbeiten Rolle authentifizierter Benutzer** . Führen Sie einen Bildlauf nach unten und aktivieren das Kontrollkästchen **Zulassen** die **Erstellen eines Web Service-Tokens** -Funktion suchen.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>Schritt 3: Bereitstellen von den Robot Moodle-Assistent für Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Die kostenlose Moodle-Assistenten Bot für Microsoft-Teams können Lehrer und Beantworten von Fragen zu ihrer Kurse, Zuordnungen, Kategorien und andere Informationen in Moodle Schüler. Der Bot sendet auch Moodle Benachrichtigungen Schüler und Lehrer innerhalb Teams. Dieser Bot ist ein open-Source-Projekt von Microsoft verwaltet und [auf GitHub verfügbar](https://github.com/microsoft/Moodle-Teams-Bot)ist.

> [!NOTE]
. In diesem Abschnitt werden Sie Ressourcen zum Azure-Abonnement bereitstellen, und alle Ressourcen verwenden die kostenlose Ebene konfiguriert werden. Je nach der Verwendung der Ihrer Bot müssen Sie diese Ressourcen zu skalieren. Wenn Sie nur die Registerkarte Moodle ohne den Robot verwenden möchten, fahren Sie mit [Schritt 4](#step-4-deploy-your-microsoft-teams-app)fort.

### <a name="moodle-bot-information-flow"></a>Moodle Bot Informationsflusses

Um den Robot zu installieren, müssen Sie auf der [Microsoft Identity-Plattform](https://identity.microsoft.com/Landing)zu registrieren. Dadurch können Ihre Bot mit Ihrem Microsoft-Endpunkten authentifizieren. So registrieren Sie Ihre Bot:

1. Zurück zu der Verwaltungsseite der-Plug-in (**websiteverwaltung** > **-Plug-Ins** > **Integration in Microsoft Office 365**), und wählen Sie die Registerkarte **Teams Settings** .
2. Klicken Sie auf der **Microsoft-Anwendung Registrierung Portal** Link und melden Sie sich mit Ihrem Microsoft-ID.
3. Geben Sie einen Namen für die app (beispielsweise MoodleBot), und klicken Sie auf die Schaltfläche **Erstellen** .
4. Kopieren Sie die **ID der Anwendung** , und fügen Sie ihn in das Feld **ID der Bot-Anwendung** auf der Seite **Einstellungen für Team** .
5. Klicken Sie auf die Schaltfläche **Neues Kennwort generieren** . Kopieren Sie das generierte Kennwort, und fügen Sie ihn in das Feld **Bot Anwendung Kennwort** auf der Seite **Einstellungen für Team** .
6. Greifen Sie auf den unteren Rand des Formulars, und klicken Sie auf **Speichern**.

Nachdem Sie Ihre Anwendung-ID und das Kennwort generiert haben, muss Ihre Bot in Azure bereitstellen werden. Klicken Sie auf die Schaltfläche **in Azure bereitstellen** und füllen Sie das Formular mit den erforderlichen Informationen (den Bot-ID und das Kennwort werden auf der Seite **Einstellungen für Team** und die Azure Informationen sind auf der Seite **Einrichten** ). Nachdem Sie das Formular ausgefüllt haben, klicken Sie auf das Kontrollkästchen, um die Geschäftsbedingungen zustimmen, und klicken Sie dann auf die Schaltfläche **Einkauf** (alle Azure Ressourcen werden an die kostenlose Schicht bereitgestellt).

Nachdem die Ressourcen abgeschlossen sind auf Azure bereitstellen, müssen Sie die Office 365 Moodle-Plug-in mit der messaging-Endpunkt zu konfigurieren. Zunächst müssen Sie den Endpunkt aus der Bot in Azure abzurufen. Gehen Sie dazu so vor:

1. Wenn Sie nicht bereits angemeldet sind, melden Sie sich mit dem [Azure-Portal](https://portal.azure.com).
2. Wählen Sie im linken Bereich **Ressourcengruppen**.
3. In der Liste Wählen Sie beim Bereitstellen Ihrer Bot die Ressourcengruppe, die Sie gerade verwendet (oder erstellt).
4. Wählen Sie die **WebApp Bot** -Ressource aus der Liste der Ressourcen in der Gruppe.
5. Kopieren Sie den **Endpunkt Messaging** , aus dem Abschnitt **Overview** .
6. Öffnen Sie in Moodle die **Team** Einstellungsseite für Ihre Office 365 Moodle-Plug-in.
7. Fügen Sie die URL, die Sie gerade kopiert, und ändern Sie die Word- *Nachrichten* in *Webhook*, im Feld **Bot-Endpunkt** . Die URL sollte nun wie folgt aussehen: `https://botname.azurewebsites.net/api/webhook`.
8. Klicken Sie auf **Änderungen zu speichern**.
9. Nachdem Sie die Änderungen gespeichert haben, wechseln Sie zurück zur Registerkarte **Team Einstellungen** , klicken Sie auf die Schaltfläche **Download manifest-Datei** , und speichern Sie das manifest-Paket auf Ihrem Computer (es im nächsten Schritt verwenden Sie).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>Schritt 4: Bereitstellen von Ihrer app Microsoft-Teams

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

Nun, dass Sie Ihre Bot in Azure bereitgestellt und konfiguriert, um auf Ihrem Server Moodle sprechen haben, ist es Zeit zum Bereitstellen von Ihrer app Microsoft-Teams. Dazu können Sie die Manifestdatei laden **Team** -Plug-in-Einstellungsseite für die Office 365 Moodle im vorherigen Schritt heruntergeladene.

Vor der Installation der app müssen Sie sicherstellen, dass externe apps und Sideloading Apps aktiviert ist. Gehen Sie hierzu [folgendermaßen](https://docs.microsoft.com/en-us/MicrosoftTeams/admin-settings)vor. Nachdem Sie sichergestellt haben, dass externe apps aktiviert sind, führen Sie die Schritte unten, um Ihre app bereitstellen.

1. Öffnen Sie Microsoft-Teams.
2. Klicken Sie auf das **Store** -Symbol auf der Navigationsleiste links unten.
3. Klicken Sie auf den Link **Hochladen eine benutzerdefinierte Anwendung** aus der Liste der Optionen. 
   > [!NOTE]
   > Wenn Sie als globaler Administrator angemeldet sind, müssen Sie die Option Hochladen der app in Ihrer Organisation app Store; Andernfalls wird nur möglich zu laden die app für die Teams, die Sie sind Teil der (*Sideloading*).
4. Wählen Sie das manifest.zip-Paket, das Sie zuvor heruntergeladen haben, und klicken Sie auf **Speichern**. Wenn Sie das manifest Paket noch nicht heruntergeladen haben, können Sie der Registerkarte **Team Einstellungen** der Konfigurationsseite-Plug-Ins in Moodle nachholen.

Nun, da Sie die app installiert haben, können Sie die Registerkarte keinen Kanal hinzufügen, denen Sie können zugreifen. Zu diesem Zweck, navigieren Sie zu den DDE-Kanal, klicken Sie auf die **+** Symbol, und wählen Sie Ihre app aus der Liste aus. Führen Sie die aufforderungen, um alle Ihre Moodle Kurs Registerkarte an einen Kanal hinzugefügt haben.

Das wars! Sie und Ihr Team können jetzt beginnen mit Ihrer Moodle Kurse direkt aus Microsoft-Teams arbeiten.

Zum Freigeben von Featureanfragen mit uns in Kontakt, oder geben Sie Feedback, besuchen Sie unsere [Benutzer VoIP-Seite](https://microsoftteams.uservoice.com/forums/916759-moodle).