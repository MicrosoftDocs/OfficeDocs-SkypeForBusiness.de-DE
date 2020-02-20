---
title: 'Lync Server 2013: definieren und Konfigurieren einer Topologie im Topologie-Generator'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34d780cd5843d69bc653cd37662c1d9332dc1fc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="619c2-102">Definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="619c2-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="619c2-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="619c2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="619c2-104">Die Ausführung des Topologie-Generators zum Definieren einer neuen Topologie oder zum Ändern einer vorhandenen Topologie erfordert keine Mitgliedschaft in einem lokalen Administrator oder einer privilegierten Domänengruppe.</span><span class="sxs-lookup"><span data-stu-id="619c2-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="619c2-105">Der Topologie-Generator führt Sie durch die Schritte, die erforderlich sind, um Ihre Topologie für ein Enterprise Edition-Front-End-Pool oder eine Standard Edition basierend auf Ihren Konfigurationsanforderungen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="619c2-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="619c2-106">Sie müssen den Topologie-Generator verwenden, um die Topologie abzuschließen und zu veröffentlichen, bevor Sie lync Server 2013 auf Servern installieren können.</span><span class="sxs-lookup"><span data-stu-id="619c2-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="619c2-107">Das folgende Verfahren umfasst die zum Definieren einer neuen Topologie erforderlichen Schritte.</span><span class="sxs-lookup"><span data-stu-id="619c2-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="619c2-108">So definieren Sie eine Topologie</span><span class="sxs-lookup"><span data-stu-id="619c2-108">To define a topology</span></span>

1.  <span data-ttu-id="619c2-109">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="619c2-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="619c2-110">Wählen Sie im Topologie-Generator die Option **neue Topologie**aus.</span><span class="sxs-lookup"><span data-stu-id="619c2-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="619c2-111">Sie werden aufgefordert, einen Speicherort und einen Dateinamen zum Speichern der Topologie anzugeben.</span><span class="sxs-lookup"><span data-stu-id="619c2-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="619c2-112">Geben Sie der Topologiedatei einen aussagekräftigen Namen, und übernehmen Sie die Standarderweiterung ".tbxml".</span><span class="sxs-lookup"><span data-stu-id="619c2-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="619c2-113">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="619c2-113">Click **OK**.</span></span>

3.  <span data-ttu-id="619c2-114">Navigieren Sie zu dem Speicherort, in dem die XML-Datei der neuen Topologie gespeichert werden soll, geben Sie einen Namen für die Datei ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="619c2-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="619c2-115">Geben Sie auf der Seite **Primäre Domäne definieren** den Namen der primären SIP-Domäne für Ihre Organisation ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="619c2-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="619c2-116">Geben Sie auf der Seite **Weitere unterstützte Domänen angeben** gegebenenfalls die Namen weiterer Domänen ein, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="619c2-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="619c2-117">Geben Sie auf der Seite **Ersten Standort definieren** einen Namen und eine Beschreibung für den ersten Standort ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="619c2-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="619c2-118">Geben Sie auf der Seite **Standortdetails angeben** die Standortinformationen für den Standort ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="619c2-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="619c2-119">Stellen Sie auf der Seite **neue Topologie wurde erfolgreich definiert** sicher, dass das Kontrollkästchen **neuen Front-End-Assistenten öffnen, wenn dieser Assistent geschlossen** wird aktiviert ist, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="619c2-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="619c2-120">Nachdem Sie die Topologie definiert und gespeichert haben, können Sie mit dem neuen Front-End-Assistenten eine Front-End-Pool oder Standard Edition-Server für Ihre Website definieren.</span><span class="sxs-lookup"><span data-stu-id="619c2-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="619c2-121">Ausführliche Informationen finden Sie unter [define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="619c2-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

