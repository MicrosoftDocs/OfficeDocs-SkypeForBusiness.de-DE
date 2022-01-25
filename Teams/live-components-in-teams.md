---
title: Verwalten von Livekomponenten in Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Livekomponenten in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b54ccf83aadcec724d8e54a791770578ef147bbd
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2022
ms.locfileid: "62191856"
---
# <a name="manage-live-components-in-teams"></a>Verwalten von Livekomponenten in Teams

Livekomponenten in Teams bieten eine neue Möglichkeit, gemeinsam Ideen zu erstellen und Entscheidungen zu treffen. Senden Sie eine Komponente , z. B. eine Tabelle, Aufgabenliste oder einen Absatz, in der jeder chat inline bearbeiten und die vorgenommenen Änderungen sehen kann. Dies bedeutet, dass Sie Ideen und Feedback von Ihrem Team sammeln können, während Sie weniger Besprechungen halten und gleichzeitig den Bedarf an langen Chatthreads minimieren.
> [!Note]
> Livekomponenten sind das erste Feature der [Microsoft Loop-App,](https://www.microsoft.com/en-us/microsoft-loop) das in Ihrer App Teams. Beachten Sie, dass "Livekomponenten" Anfang 2022 in "Schleifenkomponenten" umbenannt wird.

**Erledigen Sie Aufgaben schneller zusammen.** Sie können eine Tagesordnung aus der Menge stammen lassen, die Aktionselemente einer Gruppe nachverfolgen oder gemeinsam Notizen machen. Dies sind nur einige wenige Szenarien, die mit Livekomponenten einfacher gemacht werden.

**Teilen von Komponenten.** In dieser Version können Sie Livekomponenten in verschiedenen Chats Teams teilen. Empfänger können von überall aus bearbeiten und Aktualisierungen sofort sehen, unabhängig davon, wo die Änderungen vorgenommen wurden. In zukünftigen Versionen werden Livekomponenten in Teams Besprechungsnotizen und -kanälen, Outlook und schließlich in allen Microsoft 365 unterstützt.

**Starten Sie im Chat, erstellen Sie von dort aus.** Jede Komponente, die Sie aus Teams Chat erstellen, wird automatisch in einer Datei in OneDrive. Sie können also mit der Zusammenarbeit im Chat beginnen und später zu der Datei wechseln, in der Sie über einen größeren visuellen Bereich zum Bearbeiten verfügen und so viele Komponenten hinzufügen können, wie Sie möchten.

## <a name="clients-and-platforms"></a>Clients und Plattformen

Verfügbar für Teams-Apps Windows, Mac, Linux, iOS und Android.

## <a name="settings-management"></a>Einstellungen Verwaltung

Live-Komponenten werden mit integrierten Microsoft Fluid Framework in der gesamten Microsoft 365-Suite unterstützt und über SharePoint Online und nicht über das Teams Admin Center gesteuert.

Sie benötigen die neueste Version des [PowerShell-SharePoint Online-PowerShell-Moduls,](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) um alle flüssigen Be erfahrungen in Ihrem Mandanten zu aktivieren Office 365 deaktivieren. Microsoft Fluid Framework ist für alle **Targeted Release-Mandanten** standardmäßig EIN festgelegt. Da Livekomponenten für die Zusammenarbeit entwickelt wurden, werden die Komponenten von anderen Personen immer als bearbeitbar freigegeben, auch wenn Ihr Mandant für andere Dateitypen standardmäßig auf "Nur anzeigen" festgelegt ist. Weitere Details **finden Sie unter** dem Link Weitere Informationen neben der Einstellung.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Überprüfen, ob die Fluid Framework über das PowerShell-Cmdlet "SharePoint Online" aktiviert ist

1. [Verbinden Sie SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Überprüfen Sie, Fluid Framework aktiviert ist, indem Sie Get-SPOTenant-Cmdlet ohne Argumente ausführen.

3. Überprüfen Sie, ob der Wert von IsFluidEnabled wahr **ist.**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Aktivieren des Fluid Framework über das PowerShell SharePoint Online-PowerShell-Cmdlet

1. [Verbinden Sie SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. "Fluid aktivieren" mithilfe des Cmdlets Set-SPOTenant -IsFluidEnabled-$true 
   
   Die Änderung dauert ein kurzes Zeit, bis sie für alle Ihre Mandanz zur Anwendung kommt. 

Das Feature ist für Teams Windows, Mac, iOS und Android verfügbar. Wenn die Option aktiviert ist, wird den Benutzern eine neue Option zum Einfügen von Livekomponenten in die Erfahrung zum Verfassen von Nachrichten für diese Clients angezeigt.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Deaktivieren von Fluid Framework über SharePoint Online-PowerShell-Cmdlet

1. [Verbinden Sie SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. Deaktivieren Sie "Fluid" Set-SPOTenant das Set-SPOTenant -IsFluidEnabled-$false. 

   Die Änderung dauert ein kurzes Zeit, bis sie für alle Ihre Mandanz zur Anwendung kommt. 

Wenn Sie diese Funktion erneut aktivieren müssen, können Sie SharePoint PowerShell-Online-Cmdlets verwenden.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $true
PS C:\\WINDOWS\\system32&gt;
```
## <a name="known-issues"></a>Bekannte Probleme

- Livekomponenten im Chat können nicht mithilfe von Office-App unter Android Teams bearbeitet werden.

- Wenn die Standarddateiberechtigungen des Mandanten auf Bestimmte Personen (nur die vom Benutzer angegebenen Personen) festgelegt sind und der Absender beim Erstellen einer Komponente einige Benutzer aus der Liste Bestimmte Personen im **Berechtigungsdialogfeld** entfernt, haben diese Benutzer möglicherweise weiterhin Zugriff auf den Inhalt. Dieses Problem wurde aufgrund der Zugriffsverwaltungsbeschränkung des Berechtigungsdialogfelds behoben und wird in der zukünftigen Version behoben.

- Wenn die Richtlinieneinstellungen des Mandanten für bedingten Zugriff verhindern, dass ein Clientnetzwerk eine Verbindung mit herstellen kann, funktionieren live-Komponenten nicht wie erwartet, um Änderungen am Dienst in Echtzeit `https://pushchannel.1drv.ms` zu speichern.

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Die Suche nach Livekomponenten in Teams gibt einen Link zur Komponente in office.com zurück, nicht die Chatnachricht selbst.

- Livekomponenten sind in Partnerchats deaktiviert.

- B2B-Gäste können nicht an einer Livekomponente zusammenarbeiten, die über "Company Share Link" für sie freigegeben wird, es sei denn, der Mandant legt eine Option für externen Zugriff fest, damit B2B-Gäste dieselbe Zugriffsebene wie Mandantenmitglieder erhalten. Weitere Informationen finden Sie unter [Konfigurieren von B2B-Einstellungen für die externe Zusammenarbeit.](/azure/active-directory/external-identities/delegate-invitations#configure-b2b-external-collaboration-settings)

- Teams-Webclient wird in Kürze die vollständige Unterstützung von Live-Komponenten zur Verfügung stehen.

- Livekomponenten werden in Teams Kanälen noch nicht unterstützt, aber deren Inlinebearbeitung in Kanälen ist für zukünftige mehr Benutzererfahrungen geplant.

- Wenn die Mandanten-Standarddateiberechtigungen auf Bestimmte Personen (nur vom Benutzer **festgelegte Personen)** festgelegt sind, muss der Absender beim Kopieren des Links in die Livekomponente und beim Einfügen in einen anderen Chat das Dialogfeld "Berechtigungen" verwenden und die Empfänger zur Option Bestimmte Personen hinzufügen, um den Zugriff ordnungsgemäß zu gewähren.

- Wenn die Mandanten-Standarddateiberechtigungen auf Bestimmte Personen (nur vom Benutzer **festgelegte Personen)** festgelegt sind, muss der Absender beim Erstellen einer Livekomponente in einem Gruppenchat mit mehr als 20 Mitgliedern die Berechtigungsoptionen für die Komponente manuell auswählen.

- Livekomponenten im Chat werden nicht nur geladen, wenn die Datei in eine andere Bibliothek verschoben wurde. Wenn die Datei in einen anderen Ordner verschoben wird, wird sie weiterhin im Chat geladen.

## <a name="how-to-check-your-tenants-default-file-permissions"></a>Überprüfen der Standarddateiberechtigungen Ihres Mandanten

1. Wechseln Sie zu [Microsoft 365 Admin Center](https://admin.microsoft.com/).

2. Wählen Sie links unter **Admin Center** die Option **SharePoint.**

3. Wählen **Sie Richtlinienfreigabe** aus, und zeigen Sie unter Datei- und Ordnerlinks die  >  Standardmäßigen Dateiberechtigungen Ihres Mandanten an. 

## <a name="storage-of-fluid-files"></a>Storage von `.fluid` Dateien

**Wie `.fluid` werden gespeichert?**

In einem -Teams erstellte Livekomponenten werden von einer Datei unterstützt, die in der Datei `.fluid` des Erstellers gespeichert OneDrive for Business. Als Datei in OneDrive for Business bedeutet dies, dass Benutzer Livekomponenten (Dateien) genauso einfach erstellen, entdecken und verwalten können wie `.fluid` jedes Office Dokument.

Benutzer können über `.fluid` "Office.com" und "OneDrive for Business" nach Inhalten in OneDrive for Business.
`.fluid` Dateien funktionieren mit Daten-Governance-Features wie eDiscovery, Überwachung, Berichterstellung und gesetzliche Erkung.

`.fluid`Dateien werden jetzt auf Office.com und OneDrive for Business angezeigt, z. B. in den Bereichen Zuletzt verwendet und Empfohlen.
`.fluid`Dateien können aus der Dateiversion in früheren OneDrive for Business.

Chatteilnehmer müssen über ein OneDrive verfügen, um Livekomponenten erstellen zu können. Ohne ein gültiges OneDrive-Konto können die Chatteilnehmer möglicherweise weiterhin an einer Komponente zusammenarbeiten, die von anderen Benutzern erstellt wurde, die über ein gültiges OneDrive-Konto verfügen, aber keine eigenen erstellen können.

[Das](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) Verschieben einer Datei von OneDrive auf eine SharePoint-Website führt dazu, dass die Livekomponente `.fluid` im Chat Teams wird.

**Was geschieht, wenn der Besitzer der Datei das Unternehmen verlässt?**

[OneDrive Aufbewahrungsrichtlinien](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) gelten genauso für Dateien wie für andere vom Benutzer erstellte `.fluid` Inhalte.

**Wie werden `.fluid` Dateien freigegeben?**

Livekomponenten können in einem Chat Teams oder aus einem Chat in einen anderen kopiert werden. (Livekomponenten werden in Kanälen noch nicht unterstützt.) Sie werden standardmäßig auf die vorhandenen Berechtigungen des Mandanten festgelegt, aber benutzer können vor dem Senden Berechtigungen ändern, um sicherzustellen, dass jeder Zugriff hat.

Das Öffnen von Komponenten aus Teams-Chats in Office.com bietet am oberen Rand des Fensters Freigabefunktionen, ähnlich wie die Freigabeoptionen, die für andere Office werden.

**Was `.fluid` passiert, wenn eine Datei beschädigt oder beschädigt wird?**

Der Versionsverlauf ermöglicht es Ihnen, frühere Versionen der Datei zu überprüfen und zu kopieren.

**Welche Apps können Dateien öffnen und `.fluid` bearbeiten?**

`.fluid`Dateien können nur als Links in Ihrem Browser, z. B. Office.com, und als Livekomponenten in Teams geöffnet werden. Wenn sie heruntergeladen werden, können sie nicht erneut geöffnet werden, ohne sie zuerst wieder in den Online OneDrive for Business oder SharePoint hochzuladen.
