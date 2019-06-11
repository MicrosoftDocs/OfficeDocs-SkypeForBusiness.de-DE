---
title: Bereitstellen von lync Server 2013-Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="b451e-102">Bereitstellen von lync Server 2013-Clients</span><span class="sxs-lookup"><span data-stu-id="b451e-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b451e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b451e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b451e-104">Nachdem Sie Benutzer zu lync Server 2013 migriert haben, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="b451e-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="b451e-105">Verwenden Sie den Client Versions Filter auf dem neuen lync Server 2013-Server, um nur Clients mit den aktuellsten Updates zur Anmeldung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="b451e-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="b451e-106">Konfigurieren Sie bei Bedarf die Gruppenrichtlinieneinstellungen, die für das Client-Bootstrapping erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b451e-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="b451e-107">Ausführliche Informationen finden Sie unter [Konfigurieren von clientbootstrapping-Richtlinien in lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b451e-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="b451e-108">Die Konfiguration dieser Einstellungen ist nur erforderlich, wenn Sie vorhandene Client-Trap Ping-Richtlinien ändern möchten oder wenn Sie neue Client-Trap Ping-Richtlinien festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="b451e-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="b451e-109">Wenn Sie nicht planen, clientbootstrapping-Richtlinien zu konfigurieren, oder wenn Sie möchten, dass die Richtlinien für Legacy-Client-Trap Ping weiterhin gültig sind, ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b451e-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="b451e-110">Konfigurieren Sie andere Benutzer-und Clientrichtlinien für bestimmte Benutzer oder Gruppen von Benutzern mithilfe der lync Server 2013-Systemsteuerung, der lync Server 2013-Verwaltungsshell oder beider.</span><span class="sxs-lookup"><span data-stu-id="b451e-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="b451e-111">Ausführliche Informationen finden Sie unter [neue und geänderte Einstellungen für lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b451e-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="b451e-112">Stellen Sie die neueste Version von lync Server 2013-Clients zusammen mit den neuesten kumulativen Updates bereit.</span><span class="sxs-lookup"><span data-stu-id="b451e-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="b451e-113">Ausführliche Informationen finden Sie unter [Bereitstellen von Clients und Geräten in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b451e-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="b451e-114">Optional Wenn in Ihrer Organisation der Datenschutzmodus für den erweiterten Anwesenheitsstatus von lync Server 2013 erforderlich ist, definieren Sie nach Abschluss der Migration eine clientversionsrichtlinien Regel, um zu verhindern, dass frühere Clientversionen angemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="b451e-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="b451e-115">Aktivieren Sie dann den erweiterten Anwesenheitsdaten Schutzmodus.</span><span class="sxs-lookup"><span data-stu-id="b451e-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b451e-116">Aktivieren Sie den Datenschutzmodus für den erweiterten Anwesenheitsstatus von lync 2013 erst, nachdem jeder Benutzer in einem bestimmten Serverpool die aktuellsten Clientversionen installiert hat.</span><span class="sxs-lookup"><span data-stu-id="b451e-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

