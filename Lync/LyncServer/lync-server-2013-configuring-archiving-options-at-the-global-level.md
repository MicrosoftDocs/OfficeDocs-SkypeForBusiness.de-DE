---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen auf globaler Ebene'
description: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen auf globaler Ebene.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44b8939ec95d00afa2aa7632f4555bc6fef89834
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571741"
---
# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="9af1a-103">Konfigurieren von Archivierungsoptionen auf globaler Ebene in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9af1a-103">Configuring Archiving options at the global level in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9af1a-104">_**Letztes Änderungsstand des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="9af1a-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="9af1a-105">Wenn Sie die Archivierung zu Ihrer Topologie hinzufügen und die Topologie veröffentlichen, erstellt lync Server eine globale Konfiguration für die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="9af1a-105">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="9af1a-106">Standardmäßig sind für die globale Konfiguration keine Archivierungsoptionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9af1a-106">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="9af1a-107">Die globale Konfiguration bestimmt, welche Optionen für Ihre gesamte Bereitstellung aktiviert werden, außer Sie richten Standort- oder Poolkonfigurationen ein, die die globale Konfiguration außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="9af1a-107">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="9af1a-108">Ausführliche Informationen zur Funktionsweise von Archivierungs Konfigurationen, einschließlich der Hierarchie für globale, Standort-und Poolkonfigurationen, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9af1a-108">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9af1a-109">Sie sollten alle entsprechenden Optionen für die Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9af1a-109">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="9af1a-110">So konfigurieren Sie Archivierungsoptionen auf globaler Ebene</span><span class="sxs-lookup"><span data-stu-id="9af1a-110">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="9af1a-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="9af1a-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9af1a-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9af1a-112">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="9af1a-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server 2013 Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9af1a-113">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9af1a-114">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="9af1a-114">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="9af1a-115">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="9af1a-115">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9af1a-116">Wählen Sie unter **Archivierungseinstellung bearbeiten – Global** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungsoptionen aus:</span><span class="sxs-lookup"><span data-stu-id="9af1a-116">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="9af1a-117">**Archivierung deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="9af1a-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="9af1a-118">**IM-Sitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="9af1a-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="9af1a-119">**Chat- und Webkonferenzsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="9af1a-119">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="9af1a-120">Führen Sie außerdem auf der Seite **Archivierungseinstellung bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="9af1a-120">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="9af1a-121">Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9af1a-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="9af1a-122">Um Exchange Server zum Speichern von Archivierungsdaten zu verwenden, klicken Sie auf das Kontrollkästchen **Integration der Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="9af1a-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="9af1a-123">Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9af1a-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="9af1a-124">Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9af1a-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="9af1a-125">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9af1a-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="9af1a-126">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="9af1a-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

