---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen auf globaler Ebene'
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
ms.openlocfilehash: 59ab58cbee3479bff424e7d69d475e1d83fdd3bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a><span data-ttu-id="778ef-102">Konfigurieren von Archivierungsoptionen auf globaler Ebene in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="778ef-102">Configuring Archiving options at the global level in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="778ef-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="778ef-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="778ef-104">Wenn Sie Ihrer Topologie Archivierungsvorgänge hinzufügen und die Topologie veröffentlichen, erstellt lync Server eine globale Konfiguration für die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="778ef-104">When you add Archiving to your topology and publish the topology, Lync Server creates a global configuration for Archiving.</span></span> <span data-ttu-id="778ef-105">Standardmäßig sind in der globalen Konfiguration keine Archivierungsoptionen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="778ef-105">By default, no Archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="778ef-106">Die globale Konfiguration bestimmt, welche Optionen für Ihre gesamte Bereitstellung aktiviert werden, außer Sie richten Standort- oder Poolkonfigurationen ein, die die globale Konfiguration außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="778ef-106">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>

<span data-ttu-id="778ef-107">Ausführliche Informationen zur Funktionsweise von Archivierungs Konfigurationen, einschließlich der Hierarchie für Global-, Website-und Poolkonfigurationen, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="778ef-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="778ef-108">Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="778ef-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a><span data-ttu-id="778ef-109">So konfigurieren Sie Archivierungsoptionen auf globaler Ebene</span><span class="sxs-lookup"><span data-stu-id="778ef-109">To configure archiving options at the global level</span></span>

1.  <span data-ttu-id="778ef-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="778ef-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="778ef-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="778ef-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="778ef-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server 2013-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="778ef-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="778ef-113">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="778ef-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="778ef-114">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Global**, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="778ef-114">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="778ef-115">Wählen Sie unter **Archivierungseinstellung bearbeiten – Global** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungsoptionen aus:</span><span class="sxs-lookup"><span data-stu-id="778ef-115">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="778ef-116">**Archivierung deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="778ef-116">**Disable archiving**</span></span>
    
      - <span data-ttu-id="778ef-117">**Chatsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="778ef-117">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="778ef-118">**Chat- und Webkonferenzsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="778ef-118">**Archive IM and web conferencing sessions**</span></span>

6.  <span data-ttu-id="778ef-119">Führen Sie außerdem auf der Seite **Archivierungseinstellung bearbeiten – Global** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="778ef-119">Also on the **Edit Archiving Setting – Global** page, do the following:</span></span>
    
      - <span data-ttu-id="778ef-120">Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="778ef-120">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="778ef-121">Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .</span><span class="sxs-lookup"><span data-stu-id="778ef-121">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="778ef-122">Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="778ef-122">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="778ef-123">Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="778ef-123">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="778ef-124">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="778ef-124">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

7.  <span data-ttu-id="778ef-125">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="778ef-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

