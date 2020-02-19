---
title: 'Lync Server 2013: Verwenden von Setup-Befehlszeilenoptionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db24139be4c80b66cc03ff20d2155a00681111dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Verwenden von Setup-Befehlszeilenoptionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet. Anstelle der Setup-Befehlszeilenoptionen benutzen Sie in der Regel das Office-Anpassungstool und die Datei "Config.xml", um Produkte einzurichten und Funktionen anzupassen.

Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.

### <a name="office-setup-command-line-options"></a>Optionen der Office Setup-Befehlszeile

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option der Office Setup-Befehlszeile</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [Pfad]</p></td>
<td><p>Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.</p></td>
</tr>
<tr class="odd">
<td><p>/config [Pfad]</p></td>
<td><p>Gibt die Datei "config. xml" an, die von Setup während der Installation verwendet wird. Verwenden Sie die Option/config, um die Datei config. XML anzugeben, die Sie für lync 2013 Installationen angepasst haben, beispielsweise:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>Wird mit einer geänderten Config.xml-Datei verwendet, um das Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen. Sie können die Option "/modify" z. B. nutzen, um Lync-Funktionen hinzuzufügen oder zu entfernen.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>Führt Setup auf dem Computer des Benutzers aus, um Lync zu reparieren.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>Führt Setup aus, um Lync vom Computer des Benutzers zu entfernen.</p></td>
</tr>
</tbody>
</table>


Ausführliche Informationen zur Verwendung der Setup-Befehlszeilenoptionen finden Sie <https://go.microsoft.com/fwlink/p/?linkid=267515>unter.

</div>

<span> </span>

</div>

</div>

</div>

