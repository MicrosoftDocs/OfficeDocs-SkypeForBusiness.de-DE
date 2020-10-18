---
title: Server erneut aktivieren, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS geschlossen hat
description: Server erneut aktivieren, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS geschlossen hat.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d824845a7f89c28087a7b5d180a6ed017cb47ade
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579051"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="d8023-103">Server erneut aktivieren, nachdem der Sicherheitskonfigurations-Assistent Ports in IIS geschlossen hat</span><span class="sxs-lookup"><span data-stu-id="d8023-103">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8023-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d8023-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d8023-105">Einige lync Server 2013 Rollen werden Webdienste auf Internet Information Services (IIS) Port 4443 ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d8023-105">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="d8023-106">Durch Ausführen des lync Server-Bereitstellungs-Assistenten Bootstrapper.exe oder mithilfe des Cmdlets **enable-CsComputer** wird eine Ausnahme in der Firewall erstellt und der Port geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d8023-106">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="d8023-107">Wenn Sie dann den Assistenten für die Windows Server 2008 R2 Sicherheitskonfiguration (oder andere Sicherungsskripts) ausführen, wird Port 4443 blockiert, und externe Clients können sich nicht an Webdienste wenden.</span><span class="sxs-lookup"><span data-stu-id="d8023-107">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="d8023-108">Um den Port erneut zu öffnen, können Sie entweder die Firewall-Ausnahme direkt ändern oder den Server erneut aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d8023-108">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="d8023-109">So aktivieren Sie den Server mithilfe des Bereitstellungs-Assistenten erneut</span><span class="sxs-lookup"><span data-stu-id="d8023-109">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="d8023-110">Klicken Sie auf der Seite lync Server-Bereitstellungs-Assistent neben **Schritt 2: lync Server Komponenten einrichten oder entfernen**auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="d8023-110">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="d8023-111">Klicken Sie auf der Seite **Lync Server-Komponenten einrichten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d8023-111">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="d8023-112">Wenn der Taskstatus auf der Seite **Befehle ausführen** als abgeschlossen angezeigt wird, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="d8023-112">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d8023-113">Sie können auch bootstrapper.exe oder <STRONG>enable-CsComputer</STRONG> verwenden, um den Server erneut zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d8023-113">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

