---
title: Bereitstellen von Microsoft Teams im erforderlichen Umfang für Mitarbeiter in Service und Produktion
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: Anleitung zur Verwendung von Skripts zur Bereitstellung von Microsoft Teams für Mitarbeiter in Service und Produktion.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2496656437ddcd7035b9913781c5ebc08b26582e
ms.sourcegitcommit: 9419860f9a1c1dd2c7c444162e1d55d704e19c69
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43207064"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a>Bereitstellen von Microsoft Teams im großen Maßstab für Mitarbeiter in Service und Produktion

Müssen Sie eine große Anzahl von Benutzern schnell in Microsoft Teams einrichten und eine optimierte Umgebung für die Benutzer konfigurieren? Sie können im Handumdrehen die nachstehenden Anweisungen ausführen, um Identitäten und Teams schnell bereitzustellen sowie alle relevanten Richtlinien zuzuweisen, um die Endbenutzerumgebung zu definieren.

Dabei lernen Sie Folgendes:

- Erstellen einer großen Anzahl von Benutzern
- Erstellen einer großen Anzahl von Teams und Einrichten der entsprechenden Kanäle
- Zuweisen von Lizenzen in großem Maßstab
- Erstellen geeigneter Gruppen-Messagingrichtlinien sowie von App-Einrichtungs- und -Berechtigungsrichtlinien.
- Anwenden dieser Richtlinien auf Benutzer im großen Maßstab.
- Eine große Anzahl von Benutzern einem bestimmten Team zuweisen

> [!NOTE]
> Wenn Sie diese Informationen gelesen haben und das Gefühl haben, dass Sie Hilfe benötigen oder Fragen haben, [**klicken Sie hier**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u), um zum White Glove-Support zu gelangen.

## <a name="prerequisites"></a>Voraussetzungen

Laden Sie die Objekte von [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true) herunter.

> [!IMPORTANT]
> Die Skripts unter obigem Link werden von Microsoft im Istzustand bereitgestellt und müssen an Ihre individuellen Anforderungen angepasst werden.

## <a name="technical-requirements"></a>Technische Anforderungen

- Ihr Mandant muss über die entsprechende Anzahl von Lizenzen verfügen, die Microsoft Teams umfassen. Sollten Sie noch nicht über diese Lizenzen verfügen, folgen Sie den Anweisungen, um die [kostenlose Testversion von Office 365 E1](e1-trial-license.md) zu aktivieren.
- Der Benutzer, der diese Schritte ausführt, muss dies in der Rolle eines globalen Administrators oder eines Benutzeradministrators in Azure AD tun.
- Der Benutzer muss über die Berechtigung zum Installieren und Konfigurieren von Software auf dem lokalen Computer verfügen.

## <a name="step-by-step-process-overview"></a>Übersicht über die einzelnen Prozessschritte

1. **Einrichten der Umgebung**
    1. Herunterladen der ZIP-Datei, die die PowerShell-Beispielskripts und -Dokumentation enthält
    1. Setup der Anmeldeinformationen
    1. Konfigurieren der lokalen Umgebung
    1. Konfigurieren von PowerShell-Modulen und Umgebungsvariablen
    1. Erstellen einer App-Registrierung
1. **Erstellen und Einrichten von Microsoft Teams**
    1. Erstellen von Teams
    1. Erstellen von Kanälen für Teams
1. **Erstellen von Teamrichtlinien**
    1. Erstellen von Nachrichtenrichtlinien für Teams
    1. Erstellen von App-Einrichtungsrichtlinien für Teams
    1. Erstellen von App-Berechtigungsrichtlinien für Teams
1. **Erstellen und Einrichten von Benutzern**
    1. Erstellen von Benutzern und Sicherheitsgruppen
    1. Benutzern Lizenzen über eine gruppenbasierte Lizenzierung zuweisen
1. **Zuweisen von Benutzern und Richtlinien**
    1. Benutzer Teams zuweisen
    1. Benutzern und Gruppen Richtlinien zuweisen
1. **Testen und überprüfen**
    1. Überprüfen auf Fehler
    1. Anmelden bei Microsoft Teams mit einem Testbenutzer

## <a name="set-up-your-environment"></a>Einrichten der Umgebung

Mithilfe der folgenden Schritte können Sie Ihre Umgebung einrichten:

### <a name="download-zip-file-containing-sample-powershell-scripts"></a>Herunterladen der ZIP-Datei, die die PowerShell-Beispielskripts enthält

Bevor Sie fortfahren können, müssen Sie die Skripts von [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true) herunterladen.

### <a name="setup-credentials"></a>Setup der Anmeldeinformationen

In diesem Dokument und den Beispielskripts haben wir eine Referenzdatei erstellt, die Ihre Anmeldeinformationen enthält, um Ihnen die Arbeit zu erleichtern. Bei dieser Vorgehensweise ist es nicht erforderlich, dass Sie sich bei allen verschiedenen Dienstendpunkten authentifizieren, während sich die Anmeldeinformationen an einem lokalen Speicherort befinden. Um die folgenden Skripts ausführen zu können, müssen Sie diese Referenzdatei mit den für Sie und Ihre Umgebung spezifischen Anmeldeinformationen aktualisieren. Von jedem nachfolgenden Skript aus werden die entsprechenden Anmeldeinformationen mithilfe der von uns **GetCreds** genannten Hilfsfunktion ausgelesen, und diese werden verwendet, um eine Verbindung mit den verschiedenen Diensten herzustellen.

Es ist nicht ungewöhnlich, dass für verschiedene Dienste unterschiedliche Anmeldeinformationen erforderlich sind. Sie könnten z. B. unterschiedliche Anmeldeinformationen für Microsoft Teams, Azure AD und MS Online haben; in diesem Fall können Sie "SetCred" ausführen, um die jeweilige Anmeldeinformationsdatei mit einem eigenen aussagekräftigen Namen zu speichern.

Beispiele: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml

> [!NOTE]
> Für das für die Anmeldeinformationen verwendete Konto darf keine MFA (mehrstufige Authentifizierung) erforderlich sein.

Nachfolgend finden Sie ein Beispiel dafür, wie die verschiedenen Skripts dann die gespeicherten Anmeldeinformationen verwenden:

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

Führen Sie zum Festlegen Ihrer Anmeldeinformationen die folgenden Schritte aus:

1. Suchen Sie nach dem **SetCreds.ps1**-Skript in den ZIP-Dateiobjekten.
1. Führen Sie in PowerShell das **SetCreds.ps1**-Skript aus, um Ihre Anmeldeinformationen zu speichern.
    1. Die Aufforderung "Vorgang "Export-Clixml" ausführen..." wird angezeigt, und Sie müssen "J" (oder "Y") eingeben, um dies zu genehmigen.

### <a name="configure-the-local-environment"></a>Konfigurieren der lokalen Umgebung

1. Suchen Sie nach dem **SetConfig.ps1**-Skript in den ZIP-Dateiobjekten.
1. Führen Sie in PowerShell den folgenden Befehl aus, ersetzen Sie dabei die in der Klammer aufgeführten Einträge durch Ihre spezifischen Informationen.
    1. **SetConfig.ps1** -tenantName [your tenant name] -rootPath "[full path to the root of the git repo]"

Beispiel: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`

### <a name="configure-powershell-modules-and-environmental-variables"></a>Konfigurieren von PowerShell-Modulen und Umgebungsvariablen

Bevor Sie fortfahren, müssen Sie mehrere PowerShell-Module installieren und eine Verbindung mit diesen herstellen, einschließlich Azure AD, MSAL, MSCloudUtils und MicrosoftTeams.

1. Suchen Sie das **ConfigurePowerShellModules.ps1**-Skript in den ZIP-Dateiobjekten.
1. Bearbeiten und ersetzen Sie die folgenden Umgebungsvariablen durch Ihre Variablen:
1. Führen Sie in PowerShell das **ConfigurePowerShellModules.ps1**-Skript aus.

## <a name="create-and-set-up-teams"></a>Erstellen und Einrichten von Teams

Um mit den Mitarbeitern in Service und Produktion kommunizieren und zusammenarbeiten zu können, müssen Sie zuerst eine Reihe von Teams einrichten und diesen Standardkanäle hinzufügen. Darin besteht der nächste Schritt.

### <a name="create-teams"></a>Teams erstellen

Teams bestehen aus Personen, Inhalten und Tools innerhalb Ihrer Organisation. Für die meisten Organisationen, deren Mitarbeiter vorwiegend in Service und Produktion tätig sind, empfiehlt es sich in der Praxis, ein Team basierend auf einem physischen Standort einzurichten. Beispielsweise ein Team für jeden der folgenden Orte:

- Store
- Verteilungscenter
- Produktionswerk
- Krankenhaus
- Lebensmittelgeschäft

*Bewährte Methoden*: Bei der Planung Ihrer Teams müssen die [Limits und Spezifikationen für Teams](limits-specifications-teams.md) beachtet werden. Für kleinere Organisationen kann ein organisationsweites Team zur Optimierung der Kommunikation und zur Ergänzung einer physikalischen Standortstruktur verwendet werden. In anderen Organisationen erleichtert eine strukturierte Teams-Benennungskonvention nach physischem Standort die Unternehmenskommunikation mittels gleichzeitigem Crossposting an mehrere Teams. So können Sie z. B. nach allen Teams mit "DE" im Namen suchen und mittels Crossposting eine Nachricht an alle deutschen Standorte senden. Weitere Informationen zum Thema Crossposting finden Sie [hier](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).

#### <a name="steps-to-create-teams"></a>Schritte zum Erstellen eines Teams

1. Suchen Sie die **Teams Information.csv** in den Objekten.
1. Aktualisieren Sie die Informationen in der **Teams Information.csv**-Datei mit den spezifischen Informationen Ihrer Organisation. Bedenken Sie die zuvor erwähnten bewährten Methoden.
1. Suchen Sie das **CreateTeams.ps1**-Skript.
1. Führen Sie in PowerShell das **CreateTeams.ps1**-Skript aus.

### <a name="create-channels-for-teams"></a>Erstellen von Kanälen für Teams

Kanäle sind spezielle Bereiche innerhalb eines Teams, mit denen Unterhaltungen nach bestimmten Themen, Projekten, Fachrichtungen und mehr organisiert werden können. Jedes Team erhält automatisch einen Kanal "Allgemein". Von dort aus können Sie jedoch die Struktur entsprechend den Anforderungen Ihres Unternehmens anpassen. Eine zusätzliche Kanalstruktur kann beispielsweise Folgendes umfassen:

- **Produktion**: Sicherheit, Fertigungslinie 1, Fertigungslinie 2, Unternehmenskommunikation, Schulungen
- **Lebensmittelgeschäft**: Backwaren, Obst und Gemüse, Fleischwaren, Unternehmenskommunikation, Schulungen
- **Gesundheitsversorgung**: KrankenpflegerInnen, ÄrztInnen, Intensivstation 1, Intensivstation 2
- **Gastgewerbe**: Rezeption, Wartung, Organisation, Hoteldiener und Gepäck, Unternehmenskommunikation, Schulungen
- **Detailhandel**: Verkaufsraum, Backstore, Unternehmenskommunikation, Schulungen

> [!NOTE]
> Kanäle sollten nicht als Sicherheitsbegrenzungen betrachtet werden. Sie sind ein Mittel zum Organisieren Ihrer Mitarbeiter zum Zweck der Zusammenarbeit.

*Bewährte Methoden*: Beim Planen Ihrer Kanalstruktur ist es wichtig, dass die Dinge einfach bleiben, insbesondere, wenn Sie eine große Anzahl von Benutzern einrichten möchten. Widerstehen Sie der Versuchung, Kanäle für jede Situation, Rolle oder jedes Thema zu erstellen, um den Schulungsbedarf zu minimieren. Wählen Sie für den Anfang höchstens 3-5 Kanäle aus. Bei Bedarf können Sie später auf einfache Weise weitere Kanäle erstellen. Es ist auch durchaus in Ordnung, zunächst nur den Kanal "Allgemein" zu verwenden!

#### <a name="steps-to-create-channels-for-teams"></a>Schritte zum Erstellen von Kanälen für Teams

1. Suchen Sie nach der **TeamsChannels.csv**-Datei in den ZIP-Dateiobjekten.
1. Aktualisieren Sie die **TeamsChannels.csv**-Datei mit den spezifischen Informationen Ihrer Organisation. Bedenken Sie die zuvor erwähnten bewährten Methoden.
1. Suchen Sie nach dem **CreateTeamsChannels.ps1**-Skript in den ZIP-Dateiobjekten.
1. Führen Sie in PowerShell das **TeamsChannels.ps1**-Skript aus.

## <a name="create-teams-policies"></a>Erstellen von Teamrichtlinien

Als Administrator können Sie mithilfe von Teamrichtlinien in Microsoft Teams steuern, was Benutzer in Ihrer Organisation sehen können und wozu sie berechtigt sind. Sie können z. B. steuern, welche Anwendungen auf der linken Seite des Desktops bzw. des Webbrowsers oder auf der unteren Leiste auf mobilen Geräten angeheftet sind, um die Endbenutzererfahrung im Falle des Onboardings einer großen Anzahl von Benutzern zu vereinfachen. Einige dieser Richtlinien können mit PowerShell erstellt werden, andere hingegen müssen manuell in der Admin-Konsole von Microsoft Teams erstellt werden.

*Bewährte Methoden*: Bei jeder der folgenden Richtlinien werden in Wirklichkeit zwei Richtlinien erstellt: eine für Mitarbeiter in Service und Produktion, und eine für die entsprechenden Vorgesetzten. Sie können so viele oder so wenige Richtlinien erstellen, wie Sie möchten. Bei den meisten Kunden eignen sich zwei gut zum Starten, selbst wenn anfangs für alle Gruppen die gleichen Einstellungen festgelegt werden. Wenn einige Erfahrung mit Microsoft Teams gesammelt wurde, können Sie sich entscheiden, die Benutzererfahrung weiter zu differenzieren, und die beiden bereits erstellen getrennten Richtlinien können dies vereinfachen.

### <a name="create-teams-message-policies"></a>Erstellen von Nachrichtenrichtlinien für Teams

Nachrichtenrichtlinien werden verwendet, um zu steuern, welche Chat- und Messagingfunktionen den Benutzern in Microsoft Teams zur Verfügung stehen.

*Bewährte Methoden*: Sie können zwar die automatisch erstellte globale Standardrichtlinie verwenden, wir haben uns jedoch für eine benutzerdefinierte Richtlinie entschieden, die Sie über die nachstehenden Schritte erstellen können. Dadurch wird eine noch spezifischere, einfachere und differenziertere Benutzererfahrung für Vorgesetzte und Mitarbeiter in Service und Produktion bereitgestellt.

#### <a name="steps-to-create-teams-message-policies"></a>Schritte zum Erstellen von Nachrichtenrichtlinien für Teams

1. Suchen Sie nach der **TeamsMessagingPolicies.csv**-Datei in den ZIP-Dateiobjekten.
1. Aktualisieren Sie die **TeamsMessagingPolicies.csv**-Datei mit den spezifischen Informationen Ihrer Organisation. Weitere Informationen zu einigen der möglichen Optionen finden Sie [hier](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).
1. Suchen Sie das **CreateTeamsMessagePolicies.ps1**-Skript in den Objekten.
1. Führen Sie in PowerShell das **TeamsMessagePolicies.ps1**-Skript aus.

### <a name="create-teams-app-setup-policies"></a>Erstellen von App-Einrichtungsrichtlinien für Microsoft Teams

Als Administrator können App-Einrichtungsrichtlinien für Folgendes einrichten:

- Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind. Wählen Sie die Apps aus, die Sie anheften möchten, und legen Sie die Reihenfolge fest, in der sie angezeigt werden sollen. Durch das Anpinnen können Sie Apps vorstellen, die von Benutzern in Ihrer Organisation benötigt werden, beispielsweise Apps von Drittanbietern oder von Entwicklern in Ihrer Organisation.
- Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.

Apps werden an die App-Leiste angeheftet. Hierbei handelt es sich um die Leiste am seitlichen Rand im Microsoft Teams-Desktopclient bzw. am unteren Rand in mobilen Teams-Clients (iOS und Android).

|Microsoft Teams-Desktopclient  |         |Mobiler Microsoft Teams-Client  |
|---------|---------|---------|
|![Screenshot des Microsoft Teams-Desktopclients mit Apps, die an die *App*-Leiste angeheftet sind.](media/FLW-Teams-Desktop-Client.png)         |         |![Screenshot des Microsoft Teams-Desktopclients mit Apps, die an die *untere* Leiste angeheftet sind.](media/FLW-Teams-Mobile-Client.png) |

*Bewährte Methoden*: Richtlinien für das App-Setup werden im Microsoft Teams Admin Center verwaltet. Sie können nicht mit PowerShell erstellt werden. Sie können die globale organisationsweite Standardrichtlinie verwenden, oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Für unsere Zwecke erstellen wir zwei neue Richtlinien für jeweils Mitarbeiter und Vorgesetzte in Service und Produktion, um ihnen eine einfachere und effizientere Benutzeroberfläche zur Verfügung zu stellen. Dies erleichtert das gleichzeitige Onboarding einer großen Anzahl von Benutzern. Sie können die Benutzeroberfläche eventuell den Anforderungen Ihres Unternehmens entsprechend anpassen.

#### <a name="create-the-firstline-manager-app-setup-policy"></a>Erstellen der App-Einrichtungsrichtlinie für Vorgesetzte in Service und Produktion

Die folgenden Einstellungen können so angepasst werden, dass sie den Anforderungen Ihres Unternehmens entsprechen. Wir haben einige empfohlene Optionen auf der Grundlage bewährter Methoden ausgewählt sowie zur Erleichterung des Onboardings einer großen Anzahl neuer Benutzer. Klicken Sie [hier](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy), um weitere Informationen zu erhalten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu  **Teams-Apps** > **Einrichtungsrichtlinien**.
2. Klicken Sie auf  **Hinzufügen**.  
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein. Beispiel: **App-Einrichtungsrichtlinie für Vorgesetzte in S&P**.
![Abbildung App-Einrichtungsrichtlinie für Vorgesetzte in Service und Produktion.](media/FLW-FLM-App-Setup-Policy.png)

4. Deaktivieren Sie **Benutzerdefinierte Apps hochladen**.
5. Deaktivieren Sie **Benutzern das Anheften erlauben**.
![Abbildung des Schalter für „Benutzern das Anheften erlauben“.](media/FLW-Allow-User-Pinning.png)

6. Wenn sie noch nicht aufgeführt ist, fügen Sie die **Schichten**-App hinzu. Klicken Sie [hier](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md), um weitere Informationen zu **Schichten** zu erhalten.
![Bildschirm mit angehefteten Apps, auf dem die Schichten-App neben einer Schaltfläche zum Hinzufügen zu sehen ist.](media/FLW-Add-Pinned-Apps.png)

7. Entfernen Sie "Anrufe", falls dies angezeigt wird. Hinweis: Wenn Sie dieses Feature entfernen, wird es nicht für den Benutzer deaktiviert, sondern es wird verhindert, dass es auf der App-Leiste angezeigt wird, um die Benutzeroberfläche zu vereinfachen.
8. Ordnen Sie die Apps in der nachfolgend angegebenen Reihenfolge an, um vorzugeben, wie sie in der Microsoft Teams-App-Leiste angezeigt werden sollen, und klicken Sie dann auf  **Speichern**.
    1. Aktivität
    1. Chat
    1. Teams
    1. Kalender
    1. Schichten ![Screenshot der App-Liste für Vorgesetzte in der angegebenen Reihenfolge.](media/FLW-Manager-Pinned-Apps.png)

#### <a name="create-the-firstline-worker-app-setup-policy"></a>Erstellen der App-Einrichtungsrichtlinie für Mitarbeiter in Service und Produktion

Die folgenden Einstellungen können so angepasst werden, dass sie den Anforderungen Ihres Unternehmens entsprechen. Wir haben einige empfohlene Optionen auf der Grundlage bewährter Methoden ausgewählt sowie zur Erleichterung des Onboardings einer großen Anzahl neuer Benutzer. Klicken Sie [hier](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy), um weitere Informationen zu erhalten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu  **Teams-Apps** > **Einrichtungsrichtlinien**.
2. Klicken Sie auf  **Hinzufügen**.
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein. Beispiel: **App-Einrichtungsrichtlinie für Mitarbeiter in S&P**.
![Abbildung App-Einrichtungsrichtlinie für Mitarbeiter in Service und Produktion.](media/FLW-FLW-App-Setup-Policy.png)

4. Deaktivieren Sie **Benutzerdefinierte Apps hochladen**.
5. Deaktivieren Sie **Benutzern das Anheften erlauben**.
![Abbildung des Schalter für „Benutzern das Anheften erlauben“.](media/FLW-Allow-User-Pinning.png)

6. Wenn sie noch nicht aufgeführt ist, fügen Sie die **Schichten**-App hinzu. Klicken Sie hier, um weitere Informationen zur **Schichten**-App zu erhalten.
![Bildschirm mit angehefteten Apps, auf dem die Schichten-App neben einer Schaltfläche zum Hinzufügen zu sehen ist.](media/FLW-Add-Pinned-Apps.png)

7. Entfernen Sie ggf. "Besprechungen und Anrufe", falls dies angezeigt wird. Hinweis: Wenn Sie diese Features entfernen, werden sie nicht für den Benutzer deaktiviert, sondern es wird verhindert, dass sie auf der App-Leiste angezeigt werden, um die Benutzeroberfläche zu vereinfachen.
8. Ordnen Sie die Apps in der nachfolgend angegebenen Reihenfolge an, um vorzugeben, wie sie in der Microsoft Teams-App-Leiste angezeigt werden sollen, und klicken Sie dann auf  **Speichern**.
    1. Aktivität
    1. Chat
    1. Teams
    1. Schichten ![Screenshot der App-Liste für Mitarbeiter in der angegebenen Reihenfolge.](media/FLW-Worker-Pinned-Apps.png)

### <a name="create-app-permission-policies"></a>Erstellen von App-Berechtigungsrichtlinien

Als Administrator können Sie App-Berechtigungsrichtlinien verwenden, um zu steuern, welche Apps Microsoft Teams-Benutzern in Ihrer Organisation zur Verfügung stehen. Sie können alle oder nur bestimmte Apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht wurden, zulassen oder blockieren. Wenn Sie eine App blockieren, kann sie von Benutzern, die unter die Richtlinie fallen, nicht aus dem App-Shop für Microsoft Teams installiert werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

*Bewährte Methoden*: Richtlinien für das App-Setup werden im Microsoft Teams Admin Center verwaltet. Sie können nicht mit PowerShell erstellt werden. Sie können die globale Standardrichtlinie (Org-wide default) verwenden oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Für unsere Zwecke erstellen wir zwei neue Richtlinien für jeweils Mitarbeiter und Vorgesetzte in Service und Produktion, um eine sichere und effizientere Benutzeroberfläche bereitzustellen. Dies erleichtert das gleichzeitige Onboarding einer großen Anzahl von Benutzern. Sie können die Benutzeroberfläche natürlich den Anforderungen Ihres Unternehmens entsprechend anpassen.

#### <a name="create-the-firstline-manager-app-permission-policy"></a>Erstellen der App-Berechtigungsrichtlinie für Vorgesetzte in Service und Produktion

Die folgenden Einstellungen können so angepasst werden, dass sie den Anforderungen Ihres Unternehmens entsprechen. Hierbei handelt es sich um einige empfohlene Optionen auf der Grundlage bewährter Methoden, die zur Erleichterung des Onboardings einer großen Anzahl neuer Benutzer beitragen können. Klicken Sie [hier](teams-app-permission-policies.md), um weitere Informationen zu erhalten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu  **Teams-Apps** > **Berechtigungsrichtlinien**.
2. Klicken Sie auf  **Hinzufügen**.
![Darstellung der Seite "App-Berechtigungsrichtlinie hinzufügen" mit Abschnitten für Microsoft-, Drittanbieter-und Mandanten-Apps.](media/FLW-add-app-permission-policy.png)

3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein. Beispiel: App-Berechtigungsrichtlinie für Vorgesetzte in S&P.
4. Wählen Sie unter Microsoft-Apps **Alle Apps zulassen** aus.
5. Wählen Sie unter Drittanbieter-Apps **Alle Apps zulassen** aus.
6. Wählen Sie unter Mandanten-Apps **Alle Apps zulassen** aus.
7. Klicken Sie auf  **Speichern**.

#### <a name="create-the-firstline-worker-app-permission-policy"></a>Erstellen der App-Berechtigungsrichtlinie für Mitarbeiter in Service und Produktion

Die folgenden Einstellungen können so angepasst werden, dass sie den Anforderungen Ihres Unternehmens entsprechen. Hierbei handelt es sich um einige empfohlene Optionen auf der Grundlage bewährter Methoden, die zur Erleichterung des Onboardings einer großen Anzahl neuer Benutzer beitragen können. Klicken Sie [hier](teams-app-permission-policies.md), um weitere Informationen zu erhalten.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu  **Teams-Apps** > **Berechtigungsrichtlinien**.
2. Klicken Sie auf  **Hinzufügen**.
![Darstellung der Seite "App-Berechtigungsrichtlinie hinzufügen" mit Abschnitten für Microsoft-, Drittanbieter-und Mandanten-Apps.](media/FLW-add-app-permission-policy.png)

3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein. Beispiel: App-Berechtigungsrichtlinie für Mitarbeiter in S&P.
4. Wählen Sie unter Microsoft-Apps **Alle Apps zulassen** aus.
5. Wählen Sie unter Drittanbieter-Apps **Alle Apps blockieren** aus.
6. Wählen Sie unter Mandanten-Apps **Alle Apps zulassen** aus.
7. Klicken Sie auf  **Speichern**.

## <a name="create-and-set-up-users"></a>Erstellen und Einrichten von Benutzern

### <a name="create-user-and-security-groups"></a>Erstellen von Benutzern und Sicherheitsgruppen

Damit die Arbeit mit einer großen Anzahl von Benutzern in Microsoft Teams möglich ist, müssen Sie die Benutzer zuerst in Azure AD erstellt haben. Es gibt viele Möglichkeiten, um eine große Anzahl von Benutzern bereitzustellen, aber wir möchten Folgendes hervorheben:

- Wenn diese Benutzer bereits in einem der folgenden HR-Systeme vorhanden sind, verwenden Sie die folgenden Links, um die Bereitstellung von Benutzern einzurichten:
  - SAP-Erfolgsfaktoren – [Lernprogramm: Konfigurieren der SAP-SuccessFactors für die Bereitstellung von Active Directory-Benutzern](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).
  - Arbeitstag – [Lernprogramm: Konfigurieren des Arbeitstags für die automatische Bereitstellung](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).
- Wenn sich die Benutzerinformationen in anderen Systemen befinden, fahren Sie mit den nachstehenden Schritte fort.

Um diese Benutzer effektiver verwalten zu können, müssen Sie je eine Sicherheitsgruppen für Mitarbeiter und Vorgesetzte in Service und Produktion erstellen, und diese Benutzer direkt den Sicherheitsgruppen zuordnen, indem Sie die folgenden Schritte ausführen:

1. Suchen Sie nach der **SecurityGroups.csv**-Datei in den ZIP-Dateiobjekten.
1. Aktualisieren Sie die **SecurityGroups.csv**-Datei mit den spezifischen Informationen Ihrer Organisation.
    1. Aktualisieren Sie die Felder **MessagePolicy**, **AppPermissionPolicy** und **AppSetupPolicy** so, dass sie den zuvor erstellten Richtlinien zugeordnet sind.
    1. Aktualisieren Sie das Feld **LicensePlan**, um die Lizenzierung anzugeben, die jedem dieser Benutzer bereitgestellt werden soll. Weitere Informationen zu Produktnamen und Serviceplanbezeichnern finden Sie in der Dokumentation [hier](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).
1. Suchen Sie die **Users.csv**-Datei in den ZIP-Dateiobjekten.
1. Aktualisieren Sie die **Users.csv**-Datei mit den spezifischen Informationen Ihrer Organisation.
    1. Standardmäßig erstellt das von uns bereitgestellte Skript einen Benutzer mit einem temporären Kennwort, das bei der ersten Anmeldung geändert werden muss. Wenn Sie das Standardkennwort nicht verwenden möchten, bearbeiten Sie das **CreateUsers.ps1**-Skript entsprechend Ihren Anforderungen.
    1. Stellen Sie sicher, dass Sie das Feld "SecurityGroup" so aktualisieren, dass es dem zuvor erstellten Namen entspricht.
1. Führen Sie in PowerShell das **CreateUsers.ps1**-Skript aus den Objekten aus.

### <a name="assign-licensing-to-users-by-group-based-licensing"></a>Benutzern Lizenzen über die gruppenbasierte Lizenzierung zuweisen

Kostenpflichtige Microsoft Cloud-Dienste wie Office 365, Enterprise Mobility + Security, Dynamics 365 und andere ähnliche Produkte benötigen Lizenzen. Diese Lizenzen werden jedem Benutzer zugewiesen, der Zugriff auf diese Dienste benötigt. Zum Verwalten von Lizenzen verwenden Administratoren eines der Verwaltungsportale (Office oder Azure) sowie PowerShell-Cmdlets. Azure Active Directory (Azure AD) ist die zugrunde liegende Infrastruktur, die die Identitätsverwaltung für alle Microsoft Cloud-Dienste unterstützt. Azure AD speichert Informationen zum Lizenzzuordnungsstatus für Benutzer.

Um die Lizenzierung in großem Maßstab zu ermöglichen, umfasst Azure AD jetzt die Option der gruppenbasierten Lizenzierung, und aus diesem Grund haben wir die Sicherheitsgruppen weiter oben in diesem Artikel erstellt. Sie können einer Gruppe eine oder mehrere Produktlizenzen zuweisen. Azure AD stellt sicher, dass die Lizenzen allen Mitgliedern der Gruppe zugewiesen werden. Allen neuen Mitgliedern, die der Gruppe beitreten, werden die entsprechenden Lizenzen zugewiesen. Die Lizenzen für Mitgliedern, die die Gruppe verlassen, werden wieder entfernt. Dank dieser Lizenzierungsverwaltung ist es nicht mehr erforderlich, die Lizenzverwaltung über PowerShell so zu automatisieren, dass Änderungen in der Organisations-und Abteilungsstruktur auf Benutzerbasis berücksichtigt werden.

## <a name="assign-users-and-policies"></a>Zuweisen von Benutzern und Richtlinien

### <a name="assigning-users-to-teams"></a>Benutzer Teams zuweisen

Nachdem Sie die Benutzer und die Teams erstellt haben, ist es an der Zeit, alle Benutzer den entsprechenden Teams zuzuordnen.

1. Suchen Sie die **Users.csv**-Datei in den ZIP-Dateiobjekten, und stellen Sie sicher, in dieser Datei eine genaue Zuordnung zu Gruppen zu haben.
1. Führen Sie in PowerShell das **AssignUserstoTeams.ps1**-Skript aus den ZIP-Dateiobjekten aus.

### <a name="assign-teams-policies-to-users"></a>Benutzern Teamrichtlinien zuweisen

Jetzt, da Sie die Benutzer und die Richtlinien zum Ändern der Benutzererfahrung in Microsoft Teams erstellt haben, ist es an der Zeit, diese Richtlinien den richtigen Benutzern zuzuweisen.

1. Suchen Sie die **SecurityGroups.csv**-Datei in den ZIP-Dateiobjekten, und stellen Sie sicher, in dieser Datei eine genaue Zuordnung der Richtlinien zu Gruppen zu haben.
1. Führen Sie in PowerShell das **AssignPoliciestoUsers.ps1**-Skript aus den ZIP-Dateiobjekten aus.

## <a name="test-and-validate"></a>Testen und überprüfen

### <a name="check-for-errors"></a>Überprüfen auf Fehler

Während Sie die vorangehenden Skripts ausgeführt haben, wurden etwaige Fehler oder Ausnahmen in eine CSV-Datei geschrieben, die sich im Protokollordner der ZIP-Dateiobjekte befindet. Diese Datei kann verwendet werden, um mögliche Probleme zu untersuchen.

Eine Ausnahme könnte beispielsweise bestehen, wenn Sie versucht haben, eine Gruppe zu erstellen, die bereits in Ihrem Mandanten vorhanden war.

1. Suchen Sie den **Protokoll**-Ordner, und überprüfen Sie die eventuell enthaltenen CSV-Dateien. Wenn keine Ausnahmen aufgetreten sind, finden Sie hier auch keine Ausnahmedatei.

### <a name="login-to-teams-with-a-test-user"></a>Anmelden bei Microsoft Teams mit einem Testbenutzer

Nachdem Sie alle Schritte ausgeführt haben, ist es an der Zeit, Ihre Arbeit zu überprüfen.

1. Wählen Sie einen Benutzer aus Ihrer früheren Liste aus, und melden Sie sich mit den Anmeldeinformationen dieses Benutzers bei Microsoft Teams an.
1. Überprüfen Sie, ob das Aussehen und Verhalten von Microsoft Teams Ihren Erwartungen entspricht. Wenn dies nicht der Fall ist, überprüfen Sie die Abschnitte **Erstellen von Microsoft Teams-Richtlinien** und **Benutzern Teamrichtlinien zuweisen**.
1. Vergewissern Sie sich, dass sich der Benutzer im richtigen Team befindet. Wenn dies nicht der Fall ist, überprüfen Sie die Abschnitte **Erstellen und Einrichten von Benutzern** und **Benutzer Teams zuweisen**.
