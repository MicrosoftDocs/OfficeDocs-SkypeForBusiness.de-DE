---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen für einen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63f20dc0ae80584c1eac4489a07925e90fe3e29
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="b11c4-102">Konfigurieren von Archivierungsoptionen für einen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b11c4-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b11c4-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="b11c4-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="b11c4-104">Sie können Archivierungsoptionen angeben, die auf bestimmte Pools angewendet werden sollen, indem Sie Optionen in einer Archivierungskonfiguration für jedes dieser Pools erstellen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b11c4-104">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools.</span></span> <span data-ttu-id="b11c4-105">Eine Poolkonfiguration überschreibt die globale Konfiguration und die Standortkonfiguration, aber nur für den in der Poolkonfiguration angegebenen Pool.</span><span class="sxs-lookup"><span data-stu-id="b11c4-105">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="b11c4-106">Ausführliche Informationen zur Funktionsweise von Archivierungs Konfigurationen, einschließlich der Hierarchie für Global-, Website-und Poolkonfigurationen, finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b11c4-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b11c4-107">Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b11c4-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="b11c4-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b11c4-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="b11c4-109">So konfigurieren Sie Archivierungsoptionen auf Poolebene</span><span class="sxs-lookup"><span data-stu-id="b11c4-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="b11c4-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b11c4-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b11c4-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b11c4-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="b11c4-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server 2013-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b11c4-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b11c4-113">Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b11c4-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="b11c4-114">Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Poolkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b11c4-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="b11c4-115">Wählen Sie in **Dienst auswählen** den Pool aus, der für die Archivierung konfiguriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b11c4-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="b11c4-116">Wählen Sie unter **Neue Archivierungseinstellung** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungseinstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="b11c4-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="b11c4-117">**Archivierung deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="b11c4-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="b11c4-118">**Chatsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="b11c4-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="b11c4-119">**Chat- und Webkonferenzsitzungen archivieren**</span><span class="sxs-lookup"><span data-stu-id="b11c4-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="b11c4-120">Führen Sie außerdem auf der Seite **Neue Archivierungseinstellung** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b11c4-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="b11c4-121">Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b11c4-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="b11c4-122">Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .</span><span class="sxs-lookup"><span data-stu-id="b11c4-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="b11c4-123">Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b11c4-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="b11c4-124">Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b11c4-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="b11c4-125">Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b11c4-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="b11c4-126">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="b11c4-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

