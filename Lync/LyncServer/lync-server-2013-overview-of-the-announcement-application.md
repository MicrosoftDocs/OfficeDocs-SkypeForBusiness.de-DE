---
title: 'Lync Server 2013: Übersicht über die Ankündigungsanwendung'
description: 'Lync Server 2013: Übersicht über die Ankündigungsanwendung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15e9834be5edc67777f258f8d041e134287a891a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577251"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="155ea-103">Übersicht über die Ankündigungsanwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="155ea-103">Overview of the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="155ea-104">_**Letztes Änderungsstand des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="155ea-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="155ea-105">Wenn Sie das Ankündigungsanwendung bereitstellen, müssen Sie eine Tabelle nicht zugewiesener Nummern konfigurieren, die festlegt, welche Aktion ausgeführt werden soll, wenn jemand eine nicht zugewiesene Nummer wählt.</span><span class="sxs-lookup"><span data-stu-id="155ea-105">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="155ea-106">Die Tabelle nicht zugewiesene Nummern enthält Bereiche von Telefonnummern, die für die Organisation gültig sind, und gibt an, welche Ankündigungsanwendung jeden Bereich verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="155ea-106">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="155ea-107">Wenn ein Anrufer eine Telefonnummer wählt, die für Ihre Organisation gültig ist, jedoch keinem Benutzer zugewiesen ist, sucht lync Server die Nummer in der Routingtabelle nicht zugewiesene Nummer ab, gibt den Bereich an, in den die Zahl fällt, und leitet den Anruf an das für diesen Bereich angegebene Ankündigungsanwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="155ea-107">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Lync Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="155ea-108">Das Ankündigungsanwendung den Anruf entgegennimmt und eine Audio-Nachricht wiedergibt (wenn Sie es so konfiguriert haben) und dann entweder den Anruf trennt oder an ein vordefiniertes Ziel, beispielsweise an einen Operator, übergibt.</span><span class="sxs-lookup"><span data-stu-id="155ea-108">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="155ea-109">Sie können lync Server-Verwaltungsshell-Cmdlets verwenden, um mehrere Audionachrichten zu konfigurieren oder Ziele zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="155ea-109">You can use Lync Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="155ea-p102">Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und Sie individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in der Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht länger für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="155ea-p102">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

<span data-ttu-id="155ea-115">In lync Server 2013 wird das Ankündigungsanwendung automatisch mit dem Reaktionsgruppenanwendung installiert.</span><span class="sxs-lookup"><span data-stu-id="155ea-115">In Lync Server 2013, the Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="155ea-116">Die Anwendungen für Ankündigungen und Reaktionsgruppen sind Standardkomponenten einer Enterprise-VoIP-Bereitstellung: Wenn Sie Enterprise-VoIP bereitstellen, werden beide Anwendungen automatisch bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="155ea-116">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

