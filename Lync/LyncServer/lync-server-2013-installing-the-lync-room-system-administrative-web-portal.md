---
title: 'Lync Server 2013: Installieren des Administrator-Webportals für das lync Room-System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af0f52b940e9bcfb78048ef3a2c60f09d265073
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="65386-102">Installieren des Administrator-Webportals für das lync Room-System in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65386-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65386-103">_**Letztes Änderungsstand des Themas:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="65386-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="65386-104">Sie können das Microsoft lync Room System administrative Webportal aus dem Microsoft Download Center herunterladen [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span><span class="sxs-lookup"><span data-stu-id="65386-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="65386-105">Führen Sie die folgenden Schritte aus, um das lync Room System-Verwaltungs Webportal zu installieren.</span><span class="sxs-lookup"><span data-stu-id="65386-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="65386-106">Konfigurieren Sie den Port für vertrauenswürdige Anwendungen, indem Sie das folgende Cmdlet in lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="65386-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="65386-107">Um das Besprechungsraum Portal zu installieren, laden Sie **LyncRoomAdminPortal. exe** herunter, und führen Sie es dann als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="65386-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="65386-108">Öffnen Sie die Datei "file. config" unter folgendem Speicherort:</span><span class="sxs-lookup"><span data-stu-id="65386-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="65386-109">% Programmdateien%\\Microsoft lync Server 2013\\Webkomponenten\\-Besprechungsraum\\-\\Portal int-Handler</span><span class="sxs-lookup"><span data-stu-id="65386-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="65386-110">Ändern Sie in der Datei "file. config" den PortalUserName in den in Schritt 2 erstellten Benutzernamen unter dem Abschnitt "Konfigurieren von Voraussetzungen für das lync Room System-Verwaltungs Portal" (der empfohlene Name im Schritt lautet LRSApp):</span><span class="sxs-lookup"><span data-stu-id="65386-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="65386-111">Da das LRS-Verwaltungsportal eine vertrauenswürdige Anwendung ist, müssen Sie das Kennwort nicht in der Portal Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="65386-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="65386-112">Wenn dieser Benutzer eine andere Registrierungsstelle als die lokale Registrierungsstelle verwendet, müssen Sie die Registrierungsstelle dafür angeben, indem Sie die folgende in der Datei "Internet. config" hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="65386-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="65386-113">Wenn es sich bei dem verwendeten Port nicht um 5061 handelt, fügen Sie die folgende in der Datei "Internet. config" hinzu:</span><span class="sxs-lookup"><span data-stu-id="65386-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="65386-114">Überprüfen der Installation des Administrator-Webportals von lync Room System</span><span class="sxs-lookup"><span data-stu-id="65386-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="65386-115">Gehen Sie folgendermaßen vor, um die Installation des lync Room System-Verwaltungsportals zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="65386-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="65386-116">Navigieren Sie auf einem Front-End-Server zur folgenden URL:</span><span class="sxs-lookup"><span data-stu-id="65386-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="65386-117">https://\<FE-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="65386-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="65386-118">Es sollten keine Fehler angezeigt werden, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="65386-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="65386-119">![Anmeldebildschirm des lync Room-System Administrator Portals](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Anmeldebildschirm des lync Room-System Administrator Portals")</span><span class="sxs-lookup"><span data-stu-id="65386-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="65386-120">Wenn keine Fehler angezeigt werden, versuchen Sie von einem anderen Computer in der Topologie aus auf die folgende URL zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="65386-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="65386-121">https://\<FE-Server\>/LRS</span><span class="sxs-lookup"><span data-stu-id="65386-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="65386-122">Um auf die Seite zugreifen zu können, müssen Sie die DNS-Einträge wie unter "erforderliche DNS-Einträge für die automatische Client Anmeldung" unter [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)beschrieben hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="65386-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

