---
title: 'Lync Server 2013: Ändern vorhandener Webdienst-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa146ef8d56d080c468d8e2748355d70ef928ff2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="03069-102">Ändern vorhandener Webdienst-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03069-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03069-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="03069-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="03069-104">Sie können die Seite **Webdienst** verwenden, um die Authentifizierungsmethoden für den Zugriff auf lync Server 2013 zugehörige Webserver und Webdienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="03069-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="03069-105">Führen Sie die folgenden Schritte aus, um eine vorhandene Webdienstrichtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="03069-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="03069-106">So ändern Sie vorhandene Webdienst-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="03069-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="03069-107">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="03069-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="03069-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="03069-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="03069-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="03069-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="03069-110">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.</span><span class="sxs-lookup"><span data-stu-id="03069-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="03069-111">Klicken Sie auf der Seite **Webdienst** auf eine Konfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="03069-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="03069-112">Wählen Sie im Abschnitt **Webdiensteinstellung bearbeiten** unter **Integrierte Windows-Authentifizierung** die Option **Aushandeln**, **Integrierte Windows-Authentifizierung** oder **Keine**.</span><span class="sxs-lookup"><span data-stu-id="03069-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="03069-113">Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="03069-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="03069-114">**PIN-Authentifizierung aktivieren** – Clients werden über eine PIN authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="03069-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="03069-115">**Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.</span><span class="sxs-lookup"><span data-stu-id="03069-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="03069-116">**Download einer Zertifikatkette aktivieren** – Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.</span><span class="sxs-lookup"><span data-stu-id="03069-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="03069-117">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="03069-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03069-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03069-118">See Also</span></span>


[<span data-ttu-id="03069-119">Konfigurieren der Authentifizierung in der lync Server 2013-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="03069-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

