---
title: 'Lync Server 2013: Konfigurieren von nicht zugewiesenen Telefonnummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd933ac87addf4a2094009e9f437c29437d882a0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520232"
---
# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="50098-102">Konfigurieren von nicht zugewiesenen Telefonnummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50098-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50098-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="50098-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="50098-104">In lync Server können Sie konfigurieren, was mit eingehenden Anrufen an Telefonnummern geschieht, die für Ihre Organisation gültig sind, aber keinem Benutzer oder Telefon zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="50098-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="50098-105">Zum Konfigurieren der Verarbeitung solcher Anrufe richten Sie eine Tabelle mit nicht zugewiesenen Nummern ein.</span><span class="sxs-lookup"><span data-stu-id="50098-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="50098-106">Sie können die Tabelle verwenden, um die Anrufe an eine Ankündigungsanwendung oder an einen Exchange um Server weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="50098-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="50098-p102">Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="50098-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="50098-113">Bevor Sie die Tabelle nicht zugewiesene Nummern konfigurieren, müssen Sie bereits eine oder mehrere Ansagen definiert oder eine Exchange um automatische Telefonzentrale eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="50098-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="50098-114">Ausführliche Informationen zum Erstellen von Ankündigungen finden Sie unter <A href="lync-server-2013-create-an-announcement.md">Create a Announcement in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="50098-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="50098-115">Führen Sie das Cmdlet <STRONG>Get-CsExUmContact</STRONG> aus, um festzustellen, ob Sie Exchange um Einstellungen konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="50098-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="50098-116">Einzelheiten dazu finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span><span class="sxs-lookup"><span data-stu-id="50098-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="50098-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="50098-117">In This Section</span></span>

  - [<span data-ttu-id="50098-118">Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50098-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="50098-119">Löschen eines Bereichs nicht zugewiesener Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50098-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

