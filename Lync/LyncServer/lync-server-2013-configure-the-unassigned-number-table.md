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
ms.openlocfilehash: b99679d439257b54b6bb40d8e724bb63da4a1ea5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

In lync Server 2013 können Sie angeben, was mit eingehenden Anrufen von Telefonnummern geschieht, die für Ihre Organisation gültig sind, aber keinem Benutzer oder Telefon zugewiesen sind. Anrufer können eine Nachricht hören oder an ein anderes Ziel oder beides weiterleiten.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr dann eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.

<div>


> [!IMPORTANT]  
> Bevor Sie die Tabelle "nicht zugewiesene Nummern" konfigurieren, muss Ihr System bereits Ankündigungen definiert haben oder eine automatische UM-Telefonzentrale (Exchange Unified Messaging) eingerichtet haben.



</div>

<div>


> [!TIP]  
> Wenn jemand eine nicht zugewiesene Nummer anruft, durchsucht lync Server die Tabelle nicht zugewiesene Nummern von oben nach unten und verwendet den ersten übereinstimmenden Bereich. Sie sollten also als letzte Lösungsmöglichkeit eine Aktion definieren, die für den letzten Bereich in der Tabelle ausgeführt werden soll.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

[Erstellen oder Ändern eines nicht zugewiesenen Nummernbereichs in lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Erstellen einer Ankündigung in lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

