---
title: 'Lync Server 2013: Erstellen neuer Konfigurationseinstellungen für den Webdienst'
description: 'Lync Server 2013: Erstellen neuer Konfigurationseinstellungen für den Webdienst.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc66b0c8f394260fbe30e444f800640c774b6bcf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553961"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="53c63-103">Erstellen neuer Konfigurationseinstellungen für den Webdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53c63-103">Create new Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53c63-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="53c63-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="53c63-105">Sie können die Seite **Webdienst** verwenden, um die Authentifizierungsmethoden für den Zugriff auf lync Server 2013 zugehörige Webserver und Webdienste zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="53c63-105">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="53c63-106">Führen Sie die folgenden Schritte aus, um eine neue webdienstrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="53c63-106">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="53c63-107">So erstellen Sie neue Webdienste-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="53c63-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="53c63-108">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="53c63-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="53c63-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="53c63-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53c63-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="53c63-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53c63-111">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **Webdienst**.</span><span class="sxs-lookup"><span data-stu-id="53c63-111">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="53c63-112">Klicken Sie auf der Seite **Webdienst** auf **neu**, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="53c63-112">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="53c63-113">Klicken Sie auf **Websitekonfiguration**, um den Webdienst für eine Website zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="53c63-113">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="53c63-114">Klicken Sie unter **Standort auswählen**auf den Standort, auf den die webdienstrichtlinie angewendet werden soll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c63-114">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="53c63-115">Klicken Sie zum Konfigurieren des Webdiensts für einen Pool auf **Poolkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="53c63-115">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="53c63-116">Klicken Sie unter **Dienst auswählen**auf den Dienst, auf den die webdienstrichtlinie angewendet wird, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c63-116">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="53c63-117">Wählen Sie unter **neue Webdienst Einstellung**unter **integrierte Windows-Authentifizierung**die **Option Aushandeln**, **integrierte Windows-Authentifizierung**oder **keine**aus.</span><span class="sxs-lookup"><span data-stu-id="53c63-117">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="53c63-118">Wählen Sie je nach Funktionen der Clients und der Unterstützung in Ihrer Umgebung, eine oder mehrere der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="53c63-118">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="53c63-119">**PIN-Authentifizierung aktivieren** – Clients werden über eine PIN authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="53c63-119">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="53c63-120">**Zertifikatauthentifizierung aktivieren** – Die Server im Pool geben Zertifikate an die Clients aus.</span><span class="sxs-lookup"><span data-stu-id="53c63-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="53c63-121">**Download einer Zertifikatkette aktivieren** – Server können die Zertifikatkette für das jeweilige Zertifikat herunterladen.</span><span class="sxs-lookup"><span data-stu-id="53c63-121">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="53c63-122">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="53c63-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

