---
title: 'Lync Server 2013: Übersicht über die Ankündigungsanwendung'
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
ms.openlocfilehash: 264fbf5faf3fbce830a8d55cd7626d1ff67c2d58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Übersicht über die Ankündigungsanwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-13_

Wenn Sie das Ankündigungsanwendung bereitstellen, müssen Sie eine Tabelle nicht zugewiesener Nummern konfigurieren, die festlegt, welche Aktion ausgeführt werden soll, wenn jemand eine nicht zugewiesene Nummer wählt. Die Tabelle nicht zugewiesene Nummern enthält Bereiche von Telefonnummern, die für die Organisation gültig sind, und gibt an, welche Ankündigungsanwendung jeden Bereich verarbeitet. Wenn ein Anrufer eine Telefonnummer wählt, die für Ihre Organisation gültig ist, jedoch keinem Benutzer zugewiesen ist, sucht lync Server die Nummer in der Routingtabelle nicht zugewiesene Nummer ab, gibt an, in welchem Bereich die Zahl liegt, und leitet den Anruf an die Ansage weiter. für diesen Bereich angegebene Anwendung. Das Ankündigungsanwendung den Anruf entgegennimmt und eine Audio-Nachricht wiedergibt (wenn Sie es so konfiguriert haben) und dann entweder den Anruf trennt oder an ein vordefiniertes Ziel, beispielsweise an einen Operator, übergibt. Sie können lync Server-Verwaltungsshell-Cmdlets verwenden, um mehrere Audionachrichten zu konfigurieren oder Ziele zu übertragen.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und Sie individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in der Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht länger für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.

In lync Server 2013 wird das Ankündigungsanwendung automatisch mit dem Reaktionsgruppenanwendung installiert. Die Anwendungen für Ankündigungen und Reaktionsgruppen sind Standardkomponenten einer Enterprise-VoIP-Bereitstellung: Wenn Sie Enterprise-VoIP bereitstellen, werden beide Anwendungen automatisch bereitgestellt.

</div>

<span> </span>

</div>

</div>

</div>

