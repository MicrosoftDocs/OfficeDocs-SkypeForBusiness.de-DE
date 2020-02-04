---
title: 'Lync Server 2013: Übersicht über die Ankündigungs Anwendung'
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
ms.openlocfilehash: a4c1b9210fcb0734b305a30d27c77b4e81257909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Übersicht über die Ankündigungs Anwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-13_

Wenn Sie die Ankündigungs Anwendung bereitstellen, müssen Sie eine Tabelle mit nicht zugewiesener Nummer konfigurieren, die bestimmt, welche Aktion ausgeführt werden soll, wenn eine andere Person eine nicht zugewiesene Nummer wählt. Die Tabelle "nicht zugewiesene Nummer" enthält Bereiche von Telefonnummern, die für die Organisation gültig sind, und gibt an, welche Ankündigungs Anwendung die einzelnen Bereiche verarbeitet. Wenn ein Anrufer eine Telefonnummer wählt, die für Ihre Organisation gültig ist, aber keiner Person zugewiesen ist, sucht lync Server die Nummer in der Routingtabelle nicht zugewiesene Nummer, gibt den Bereich an, in den die Zahl fällt, und leitet den Anruf an die Ansage weiter für diesen Bereich angegebene Anwendung. Die Ankündigungs Anwendung beantwortet den Anruf und gibt eine Audionachricht wieder, wenn Sie Sie so konfiguriert haben, und trennt dann entweder den Anruf oder übergibt ihn an ein festgelegtes Ziel, beispielsweise an einen Operator. Sie können Cmdlets der lync Server-Verwaltungsshell verwenden, um mehrere Audionachrichten zu konfigurieren oder Ziele zu übertragen.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie sie verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in die Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht mehr für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.

In lync Server 2013 wird die Ankündigungs Anwendung automatisch mit der reaktionsgruppenanwendung installiert. Die Anwendungen für Ankündigungen und Reaktionsgruppen sind Standardkomponenten einer Enterprise-VoIP-Bereitstellung: Wenn Sie Enterprise-VoIP bereitstellen, werden diese beiden Anwendungen automatisch bereitgestellt.

</div>

<span> </span>

</div>

</div>

</div>

