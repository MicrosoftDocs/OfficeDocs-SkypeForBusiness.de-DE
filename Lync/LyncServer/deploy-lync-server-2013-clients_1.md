---
title: Bereitstellen von lync Server 2013 Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac6dce30e356ed3161f985f32d8f26dc0e34ac6d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="7d8f9-102">Bereitstellen von lync Server 2013 Clients</span><span class="sxs-lookup"><span data-stu-id="7d8f9-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d8f9-103">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7d8f9-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7d8f9-104">Nachdem Sie Benutzer zu lync Server 2013 migriert haben, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7d8f9-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="7d8f9-105">Verwenden Sie den Client Versions Filter auf dem neuen lync Server 2013 Server, um nur Clients mit den aktuellsten Updates zur Anmeldung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="7d8f9-106">Konfigurieren Sie, falls erforderlich, die Gruppenrichtlinieneinstellungen, die für das Clientbootstrapping benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="7d8f9-107">Ausführliche Informationen finden Sie unter [Configuring clientbootstrapping Policies in lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="7d8f9-108">Diese Einstellungen müssen nur dann konfiguriert werden, wenn Sie vorhandene Clientbootstrapping-Richtlinien ändern oder neue Clientbootstrapping-Richtlinien festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="7d8f9-109">Wenn Sie keine Clientbootstrapping-Richtlinien konfigurieren möchten oder Clientbootstrapping-Richtlinien der Vorgängerversion gültig bleiben sollen, ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="7d8f9-110">Konfigurieren Sie andere Benutzer-und Clientrichtlinien für bestimmte Benutzer oder Benutzergruppen mithilfe lync Server 2013 Systemsteuerung, lync Server 2013 Verwaltungsshell oder beides.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="7d8f9-111">Ausführliche Informationen finden Sie unter [neue und geänderte Einstellungen für lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="7d8f9-112">Stellen Sie die neueste Version von lync Server 2013-Clients zusammen mit den neuesten kumulativen Updates bereit.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="7d8f9-113">Ausführliche Informationen finden Sie unter [Deploying Clients and Devices in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="7d8f9-114">Optional Wenn Ihre Organisation lync Server 2013 erweiterten Datenschutzmodus für Anwesenheitsinformationen benötigt, definieren Sie nach Abschluss der Migration eine Richtlinienregel für Clientversionen, um zu verhindern, dass frühere Clientversionen sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="7d8f9-115">Aktivieren Sie dann den Datenschutzmodus für erweiterte Anwesenheitsinformationen.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7d8f9-116">Aktivieren Sie lync 2013 erweiterten Datenschutzmodus für Anwesenheitsinformationen erst, wenn jeder Benutzer in einem bestimmten Serverpool die neuesten Clientversionen installiert hat.</span><span class="sxs-lookup"><span data-stu-id="7d8f9-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

