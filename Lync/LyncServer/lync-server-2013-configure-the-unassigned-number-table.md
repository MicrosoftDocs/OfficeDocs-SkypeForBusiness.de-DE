---
title: 'Lync Server 2013: Konfigurieren der Tabelle nicht zugewiesener Nummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb3aa60273439c94a5d936efe826e77dcc683be
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="5dc5d-102">Konfigurieren der Tabelle nicht zugewiesener Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dc5d-102">Configure the unassigned number table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dc5d-103">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="5dc5d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="5dc5d-104">In lync Server 2013 können Sie angeben, was mit eingehenden Anrufen an Telefonnummern geschieht, die für Ihre Organisation gültig sind, aber keinem Benutzer oder Telefon zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="5dc5d-105">Anrufer können eine Nachricht hören, oder Sie können an ein anderes Ziel oder beides weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="5dc5d-106">Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-106">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="5dc5d-107">Sie können die Tabelle mit allen gültigen Erweiterungen für Ihre Organisation konfigurieren, mit nur nicht zugewiesenen Durchwahlnummern oder mit einer Kombination aus beiden Nummerntypen.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-107">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="5dc5d-108">Die Tabelle nicht zugewiesene Nummern kann sowohl zugewiesene als auch nicht zugewiesene Nummern enthalten, wird jedoch nur dann aufgerufen, wenn ein Anrufer eine Nummer wählt, die derzeit nicht zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-108">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="5dc5d-109">Wenn Sie alle gültigen Erweiterungen in die Tabelle nicht zugewiesene Nummern einschließen, können Sie die Aktion angeben, die bei jedem verlassen einer Organisation auftritt, ohne die Tabelle neu konfigurieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-109">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="5dc5d-110">Wenn Sie nicht zugewiesene Erweiterungen in die Tabelle einschließen, können Sie die Aktion ändern, die für bestimmte Nummern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-110">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="5dc5d-111">Wenn Sie beispielsweise die Durchwahl für Ihren Kundendienst ändern, können Sie die alte Kundendienstnummer in die Tabelle einbeziehen und diese dann einer Ankündigung zuweisen, die die neue Nummer bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-111">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5dc5d-112">Bevor Sie die Tabelle nicht zugewiesene Nummern konfigurieren, muss Ihr System bereits Ankündigungen definiert haben oder eine Exchange Unified Messaging (um) automatische Telefonzentrale eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="5dc5d-113">Wenn ein Benutzer eine nicht zugewiesene Nummer anruft, sucht lync Server die Tabelle nicht zugewiesener Nummern von oben nach unten und verwendet den ersten übereinstimmenden Bereich.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="5dc5d-114">Daher sollte eine Aktion, die Sie als letztes Mittel durchführen möchten, für den letzten Bereich in der Tabelle angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5dc5d-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5dc5d-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5dc5d-115">In This Section</span></span>

<span data-ttu-id="5dc5d-116">[Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Erstellen einer Ansage in lync Server 2013](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="5dc5d-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

