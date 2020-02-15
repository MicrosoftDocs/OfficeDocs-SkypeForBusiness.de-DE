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

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Konfigurieren der Tabelle nicht zugewiesener Nummern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

In lync Server 2013 können Sie angeben, was mit eingehenden Anrufen an Telefonnummern geschieht, die für Ihre Organisation gültig sind, aber keinem Benutzer oder Telefon zugewiesen sind. Anrufer können eine Nachricht hören, oder Sie können an ein anderes Ziel oder beides weitergeleitet werden.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Erweiterungen für Ihre Organisation konfigurieren, mit nur nicht zugewiesenen Durchwahlnummern oder mit einer Kombination aus beiden Nummerntypen. Die Tabelle nicht zugewiesene Nummern kann sowohl zugewiesene als auch nicht zugewiesene Nummern enthalten, wird jedoch nur dann aufgerufen, wenn ein Anrufer eine Nummer wählt, die derzeit nicht zugewiesen ist. Wenn Sie alle gültigen Erweiterungen in die Tabelle nicht zugewiesene Nummern einschließen, können Sie die Aktion angeben, die bei jedem verlassen einer Organisation auftritt, ohne die Tabelle neu konfigurieren zu müssen. Wenn Sie nicht zugewiesene Erweiterungen in die Tabelle einschließen, können Sie die Aktion ändern, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahl für Ihren Kundendienst ändern, können Sie die alte Kundendienstnummer in die Tabelle einbeziehen und diese dann einer Ankündigung zuweisen, die die neue Nummer bereitstellt.

<div>


> [!IMPORTANT]  
> Bevor Sie die Tabelle nicht zugewiesene Nummern konfigurieren, muss Ihr System bereits Ankündigungen definiert haben oder eine Exchange Unified Messaging (um) automatische Telefonzentrale eingerichtet haben.



</div>

<div>


> [!TIP]  
> Wenn ein Benutzer eine nicht zugewiesene Nummer anruft, sucht lync Server die Tabelle nicht zugewiesener Nummern von oben nach unten und verwendet den ersten übereinstimmenden Bereich. Daher sollte eine Aktion, die Sie als letztes Mittel durchführen möchten, für den letzten Bereich in der Tabelle angegeben werden.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

[Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Erstellen einer Ansage in lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

