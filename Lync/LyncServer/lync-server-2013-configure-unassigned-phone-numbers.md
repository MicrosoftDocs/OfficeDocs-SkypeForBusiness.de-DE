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
ms.openlocfilehash: 920dc38010aa82f7c3f970a76f78c23bbf2a486a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Konfigurieren von nicht zugewiesenen Telefonnummern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

In lync Server können Sie konfigurieren, was mit eingehenden Anrufen an Telefonnummern geschieht, die für Ihre Organisation gültig sind, aber keinem Benutzer oder Telefon zugewiesen sind. Zum Konfigurieren der Verarbeitung solcher Anrufe richten Sie eine Tabelle mit nicht zugewiesenen Nummern ein. Sie können die Tabelle verwenden, um die Anrufe an eine Ankündigungsanwendung oder an einen Exchange um Server weiterzuleiten.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.

<div>


> [!IMPORTANT]  
> Bevor Sie die Tabelle nicht zugewiesene Nummern konfigurieren, müssen Sie bereits eine oder mehrere Ansagen definiert oder eine Exchange um automatische Telefonzentrale eingerichtet haben. Ausführliche Informationen zum Erstellen von Ankündigungen finden Sie unter <A href="lync-server-2013-create-an-announcement.md">Create a Announcement in lync Server 2013</A>. Führen Sie das Cmdlet <STRONG>Get-CsExUmContact</STRONG> aus, um festzustellen, ob Sie Exchange um Einstellungen konfiguriert haben. Einzelheiten dazu finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Löschen eines Bereichs nicht zugewiesener Nummern in lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

