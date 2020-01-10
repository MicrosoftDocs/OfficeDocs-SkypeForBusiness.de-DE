---
title: Konfigurieren von SharePoint Server für die Suche nach archivierten Skype for Business-Daten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 'Zusammenfassung: Konfigurieren Sie SharePoint Server für die Suche nach Daten, die von Exchange Server und Skype for Business Server archiviert werden.'
ms.openlocfilehash: d896d6acecd808e5b153e931b8c4b3a8ba62ed9a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003575"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a><span data-ttu-id="b6c2a-103">Konfigurieren von SharePoint Server für die Suche nach archivierten Skype for Business-Daten</span><span class="sxs-lookup"><span data-stu-id="b6c2a-103">Configure SharePoint Server to search for archived Skype for Business data</span></span>
 
<span data-ttu-id="b6c2a-104">**Zusammenfassung:** Konfigurieren Sie SharePoint Server für die Suche nach Daten, die von Exchange Server 2016 oder Exchange Server 2013 und Skype for Business Server archiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-104">**Summary:** Configure SharePoint Server to search for data archived by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="b6c2a-105">Einer der Hauptvorteile für das Speichern von Instant Messaging-und Webkonferenz Protokollen in Exchange Server anstelle von Skype for Business Server besteht darin, dass Administratoren mithilfe eines einzigen Tools nach archivierten Exchange-Daten und/oder archivierten Skype for Business Server-Daten suchen können.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-105">One of the major advantages to storing instant messaging and Web conferencing transcripts in Exchange Server instead of Skype for Business Server is that storing data in the same location allows administrators to use a single tool to search for archived Exchange data and/or archived Skype for Business Server data.</span></span> <span data-ttu-id="b6c2a-106">Da alle Daten an derselben Stelle (Exchange) gespeichert sind, können alle Tools, die nach archivierten Exchange-Daten suchen können, auch nach archivierten Skype for Business Server-Daten suchen.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-106">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Skype for Business Server data.</span></span>
  
<span data-ttu-id="b6c2a-107">Ein Tool, mit dem Sie nach archivierten Daten einfach suchen können, ist Microsoft SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-107">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="b6c2a-108">Wenn Sie SharePoint für die Suche nach Skype for Business Server-Daten verwenden möchten, müssen Sie zunächst alle Schritte ausführen, die bei der Konfiguration der Exchange-Archivierung in Skype for Business Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-108">If you would like to use SharePoint to search for Skype for Business Server data, you must first complete all the steps involved in configuring Exchange archiving in Skype for Business Server.</span></span> <span data-ttu-id="b6c2a-109">Nachdem Exchange Server und Skype for Business Server erfolgreich integriert wurden, müssen Sie die verwaltete API für Exchange [-Webdienste](https://go.microsoft.com/fwlink/p/?LinkId=258305) auf dem SharePoint-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-109">After Exchange Server and Skype for Business Server have been successfully integrated, you must then install the Exchange [Web Services Managed API](https://go.microsoft.com/fwlink/p/?LinkId=258305) on your SharePoint Server.</span></span> <span data-ttu-id="b6c2a-110">Die heruntergeladene Datei (EWSManagedAPI.msi) kann in einem beliebigen Ordner auf Ihrem SharePoint-Server gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-110">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>
  
<span data-ttu-id="b6c2a-111">Wenn die Datei vollständig heruntergeladen ist, führen Sie auf dem SharePoint-Server folgendes Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-111">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>
  
1. <span data-ttu-id="b6c2a-112">Öffnen Sie ein Befehlsfenster. Klicken Sie dazu auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-112">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>
    
2. <span data-ttu-id="b6c2a-113">Verwenden Sie im Befehlsfenster den Befehl cd, um das aktuelle Verzeichnis in den Ordner zu ändern, in dem die Datei „EWSManagedAPI.msi“ gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-113">In the command window, use the cd command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="b6c2a-114">Wenn Sie beispielsweise die Datei auf C:\Downloads gespeichert haben, geben Sie den folgenden Befehl im Befehlsfenster ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-114">For example, if you have saved the file to C:\Downloads type the following command in the command window and then press Enter:</span></span>
    
   ```console
   cd C:\Downloads
   ```

3. <span data-ttu-id="b6c2a-115">Zum Installieren der API geben Sie den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-115">To install the API, type the following command then press Enter:</span></span>
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. <span data-ttu-id="b6c2a-116">Nachdem die API installiert wurde, setzen Sie IIS zurück, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-116">After the API has been installed, reset IIS by typing the following command and pressing Enter:</span></span>
    
   ```console
   iisreset
   ```

<span data-ttu-id="b6c2a-117">Nachdem Exchange-Webdienste installiert wurden, müssen Sie die Server-zu-Server-Authentifizierung zwischen SharePoint Server und Exchange Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-117">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server and Exchange Server.</span></span> <span data-ttu-id="b6c2a-118">Öffnen Sie dazu zunächst die SharePoint-Verwaltungsshell, und führen Sie die folgenden Befehlssätze aus:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-118">To do this, first open the SharePoint Management Shell and run the following set of commands:</span></span>
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> <span data-ttu-id="b6c2a-119">Achten Sie darauf, den URI für Ihren AutoErmittlungsdienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-119">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="b6c2a-120">Verwenden Sie den Beispiel-URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1nicht.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-120">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span> 
  
<span data-ttu-id="b6c2a-121">Nachdem Sie den Token-Aussteller erstellt und den Tokendienst konfiguriert haben, führen Sie diese Befehle aus, und stellen Sie sicher, dass Sie die URL Ihrer SharePoint-Website für die Beispiel-URL ersetzen.http://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-121">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

<span data-ttu-id="b6c2a-122">Wenn Sie die Server-zu-Server-Authentifizierung für Exchange Server konfigurieren möchten, öffnen Sie die Exchange-Verwaltungsshell, und führen Sie einen ähnlichen Befehl aus (vorausgesetzt, Exchange wurde auf Laufwerk C: installiert und verwendet den Standardordnerpfad):</span><span class="sxs-lookup"><span data-stu-id="b6c2a-122">To configure server-to-server authentication for Exchange Server, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

<span data-ttu-id="b6c2a-123">Nachdem Sie die Partneranwendung konfiguriert haben, empfiehlt es sich, Internet Informationsdienste (IIS) auf allen Exchange-Post Fach-und Clientzugriffsservern zu beenden und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-123">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="b6c2a-124">Sie können IIS neu starten, indem Sie einen ähnlichen Befehl verwenden, mit dem der Dienst auf dem Computer "ATL-Exchange-001" neu gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-124">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>
  
```powershell
iisreset atl-exchange-001
```

<span data-ttu-id="b6c2a-125">Dieser Befehl kann in der Exchange-Verwaltungsshell oder in einem anderen Befehlsfenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-125">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>
  
<span data-ttu-id="b6c2a-126">Führen Sie als nächstes einen Befehl aus, der dem folgenden ähnelt, wodurch der angegebene Benutzer (in diesem Beispiel kenmyer) das Recht hat, eine Ermittlung in Exchange durchzuführen:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-126">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

<span data-ttu-id="b6c2a-127">Nachdem die Server-zu-Server-Authentifizierung zwischen Exchange und SharePoint hergestellt wurde, besteht der nächste Schritt darin, eine eDiscovery-Website in SharePoint zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-127">After server-to-server authentication has been established between Exchange and SharePoint, your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="b6c2a-128">Dies kann durch Ausführen von Befehlen ähnlich wie in der SharePoint-Verwaltungsshell erfolgen:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-128">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> <span data-ttu-id="b6c2a-129">„eDiscovery“ steht für „electronic Discovery“ (elektronische Ermittlung) und bezeichnet in der Regel das Durchsuchen von elektronischen Archiven nach Elementen, die in einem Gerichtsverfahren als Beweismittel zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-129">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span> 
  
<span data-ttu-id="b6c2a-130">Wenn die neue Website fertig ist, besteht der nächste Schritt darin, Exchange Server so zu konfigurieren, dass Sie als ergebnisquelle für SharePoint fungiert.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-130">When the new site is ready, the next step is to configure Exchange Server to act as a result source for SharePoint.</span></span> <span data-ttu-id="b6c2a-131">Sie können dies tun, indem Sie auf der Seite SharePoint-zentral Administration die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-131">You can do that by completing the following procedure from the SharePoint Central Administration page:</span></span>
  
1. <span data-ttu-id="b6c2a-132">Klicken Sie auf der Seite „Zentraladministration“ auf **Dienstanwendungen verwalten** und dann auf **Suchdienstanwendung**.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-132">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>
    
2. <span data-ttu-id="b6c2a-133">Klicken Sie auf der Seite „Suchdienstanwendung: Suchverwaltung“ auf **Ergebnisquellen** und dann auf **Neue Ergebnisquelle**.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-133">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>
    
3. <span data-ttu-id="b6c2a-134">Geben Sie im Bereich **Neue Ergebnisquelle** im Feld **Name** einen Namen für die neue Ergebnisquelle ein (z. B. **Microsoft Exchange**).</span><span class="sxs-lookup"><span data-stu-id="b6c2a-134">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="b6c2a-135">Wählen Sie **Exchange** als Ergebnis Quell **Protokoll**aus, und geben Sie dann im Feld **Exchange-Quell-URL** die URL des Webdienste-Quellcodes für Ihren Exchange-Server ein.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-135">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="b6c2a-136">Die Quell-URL sollte in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-136">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. <span data-ttu-id="b6c2a-137">Stellen Sie sicher, dass **AutoErmittlung verwenden** nicht ausgewählt ist, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-137">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>
    
<span data-ttu-id="b6c2a-138">Erstellen Sie schließlich einen neuen eDiscovery-Fall und einen neuen eDiscovery-Satz, indem Sie das folgende Verfahren auf der SharePoint-Ermittlungs Website ausführen (beispielsweisehttps://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="b6c2a-138">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>
  
1. <span data-ttu-id="b6c2a-139">Klicken Sie auf der Seite **Websiteinhalte** auf Neuen Fall erstellen.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-139">On the Site Contents page click **Create a new case**.</span></span>
    
2. <span data-ttu-id="b6c2a-p110">Geben Sie auf der Seite „Websiteinhalte: Neue SharePoint-Website“ im Feld **Titel** den E-Mail-Alias des Benutzers (z. B. **kenmyer**) ein und geben Sie im Feld **Websiteadresse** dieselbe URL ein. Das Ergebnis ist eine ähnliche URL wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="b6c2a-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. <span data-ttu-id="b6c2a-142">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-142">Click **Create**.</span></span>
    
4. <span data-ttu-id="b6c2a-143">Wenn die Seite „eDiscovery-Satz“ angezeigt wird, klicken Sie unter **Identifizieren und beibehalten: eDiscovery-Sätze** auf **Neues Element**.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-143">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>
    
5. <span data-ttu-id="b6c2a-144">Geben Sie auf der Seite „Neu: eDiscovery-Satz“ im Feld **Name für eDiscovery-Satz** den E-Mail-Alias des Benutzers ein.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-144">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="b6c2a-145">Geben Sie **eDiscovery\\lync**\* in das Feld **Filter** ein, und klicken Sie dann auf \*\*Verwalten von Quellen hinzufügen &amp; \*\*.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-145">Enter **eDiscovery Lync\\**\* in the **Filter** box and then click **Add &amp; Manage Sources**.</span></span>
    
6. <span data-ttu-id="b6c2a-146">Geben Sie auf &amp; der Seite Manage sources hinzufügen den e-Mail-Alias des Benutzers im ersten Textfeld unter **Postfächer**ein.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-146">On the Add &amp; Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="b6c2a-147">Klicken Sie neben dem Textfeld auf das Symbol „Postfach überprüfen“, um sicherzustellen, dass SharePoint eine Verbindung mit dem angegebenen Postfach herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-147">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>
    
7. <span data-ttu-id="b6c2a-148">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-148">Click **OK**.</span></span>
    
8. <span data-ttu-id="b6c2a-149">Klicken Sie auf der Seite „eDiscovery-Satz“ auf **Speichern**, um den neuen eDiscovery-Satz zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-149">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>
    
<span data-ttu-id="b6c2a-150">An diesem Punkt können Sie das angegebene Postfach (kenmyer) durchsuchen und/oder in-situ-Speicher auf die gleiche Weise aktivieren wie für andere SharePoint-Inhalte oder-Ergebnisquellen.</span><span class="sxs-lookup"><span data-stu-id="b6c2a-150">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>
  

