---
title: 'Lync Server 2013: Konfigurieren von AD FS 2.0 zur Unterstützung der Clientauthentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7054bae609b5d1a1c6fe176c1092614f5d30fa6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="2e9d6-102">Konfigurieren AD FS 2.0 zur Unterstützung der Clientauthentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e9d6-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e9d6-103">_**Letztes Änderungsstand des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="2e9d6-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="2e9d6-104">Es gibt zwei mögliche Authentifizierungstypen, die so konfiguriert werden können, dass AD FS 2.0 die Authentifizierung mithilfe von Smartcards unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2e9d6-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="2e9d6-105">Formularbasierte Authentifizierung (FBA)</span><span class="sxs-lookup"><span data-stu-id="2e9d6-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="2e9d6-106">Transport Layer Security-Client Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2e9d6-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="2e9d6-107">Mithilfe der formularbasierten Authentifizierung können Sie eine Webseite entwickeln, die es Benutzern ermöglicht, sich entweder mithilfe Ihres Benutzernamens/Kennworts oder mithilfe Ihrer Smartcard und PIN zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="2e9d6-108">In diesem Thema wird die Implementierung der Transport Layer Security-Client Authentifizierung mit AD FS 2.0 behandelt.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="2e9d6-109">Weitere Informationen zu AD FS 2.0 Authentifizierungstypen finden Sie unter AD FS 2.0: Ändern des lokalen Authentifizierungstyps unter [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span><span class="sxs-lookup"><span data-stu-id="2e9d6-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="2e9d6-110">**So konfigurieren Sie AD FS 2.0 zur Unterstützung der Client Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="2e9d6-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="2e9d6-111">Melden Sie sich mit einem Domänenadministratorkonto beim AD FS 2.0 Computer an.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="2e9d6-112">Starten Sie Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="2e9d6-113">Navigieren Sie zu C\\:\\Verzeichnis Inetpub\\adfs ls</span><span class="sxs-lookup"><span data-stu-id="2e9d6-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="2e9d6-114">Erstellen Sie eine Sicherungskopie der vorhandenen Datei "Internet. config".</span><span class="sxs-lookup"><span data-stu-id="2e9d6-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="2e9d6-115">Öffnen Sie die vorhandene Datei "Internet. config" mit Editor.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="2e9d6-116">Klicken Sie in der Menüleiste auf **Bearbeiten** , und wählen Sie dann **Suchen**aus.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="2e9d6-117">Suchen Sie \*\* \<nach\>localAuthenticationTypes\*\*.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="2e9d6-118">Beachten Sie, dass vier Authentifizierungstypen aufgeführt werden: eine pro Reihe.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="2e9d6-119">Verschiebt die Position mit dem TLSClient-Authentifizierungstyp an den Anfang der Liste im Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="2e9d6-120">Speichern und schließen Sie die Datei "Internet. config".</span><span class="sxs-lookup"><span data-stu-id="2e9d6-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="2e9d6-121">Starten Sie eine Eingabeaufforderung mit erhöhten Rechten.</span><span class="sxs-lookup"><span data-stu-id="2e9d6-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="2e9d6-122">Starten Sie IIS neu, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="2e9d6-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

