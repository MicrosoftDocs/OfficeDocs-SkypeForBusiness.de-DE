---
title: 'Lync Server 2013: Windows PowerShell-und lync Server-Verwaltungstools'
description: 'Lync Server 2013: Windows PowerShell-und lync Server-Verwaltungstools.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c8d63974ad05a041eb446182cbc7f9336044b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546041"
---
# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell-und lync Server 2013-Verwaltungstools

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-07-20_

In Microsoft lync Server 2013 werden Verwaltungstools mithilfe von Windows PowerShell implementiert. Windows PowerShell bietet eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Lync Server 2013 Tools, die mit Windows PowerShell implementiert werden, umfassen Folgendes:

  - **Topologie-Generator**. Mithilfe des Topologie-Generators können Sie die geplante Topologie erstellen, anpassen und veröffentlichen und Ihre Topologie überprüfen, bevor Sie mit der Server Installation beginnen. Wenn Sie lync Server 2013 auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server wie in der Topologie weitergeleitet bereit. Nach dem Setup werden Konfigurationsinformationen automatisch auf alle Server repliziert. Komponenten können nur mithilfe des Topologie-Generators zur Bereitstellung hinzugefügt werden.

  - **Lync Server-Verwaltungsshell**. Sie können lync Server-Verwaltungsshell für die vollständige Befehlszeilenverwaltung Ihrer Bereitstellung verwenden.

  - **Lync Server-Systemsteuerung**. Sie können die Benutzeroberfläche der Microsoft lync Server 2013 Systemsteuerung verwenden, um die am häufigsten verwendeten Aufgaben in Ihrer Bereitstellung zu verwalten.

In diesen Tools werden Windows PowerShell-Cmdlets für die Verwaltung einer Bereitstellung verwendet, darunter fast 550 produktspezifische Cmdlets. Die in lync Server 2013 enthaltenen Sicherheits-Cmdlets dienen in erster Linie zum Verwalten der Authentifizierung sowie von Benutzerrechten und-Berechtigungen. Zum Verwalten der Authentifizierung stehen zahlreiche Cmdlets zur Verfügung, darunter Cmdlets für die Authentifizierung unter Verwendung von Zertifikaten oder einer persönlichen Identifikationsnummer (PIN). Darüber hinaus können Sie mit einer Reihe von Cmdlets die neue Funktion für die Role-Based Zugriffssteuerung (RBAC) verwenden, um die administrative Steuerung von lync Server 2013 zu delegieren. Ausführliche Informationen zu den lync Server-Cmdlets finden Sie unter [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

Die skriptbezogenen Sicherheitsfeatures für Windows PowerShell wurden speziell entwickelt, um einige der mit Skripts zusammenhängenden Sicherheitsprobleme in älteren Technologien zu vermeiden, z, B. in Microsoft Visual Basic Scripting Edition (VBScript). Die Windows PowerShell-Sicherheitsfeatures sollen Ihnen helfen, eine Umgebung aufzubauen, in der es den Benutzern nicht möglich ist, auf einfache Weise oder unwissentlich Skripts auszuführen. Standardmäßig sind Windows PowerShell-Sicherheitsfeatures aktiviert. Sie können den Status dieser Features ändern, um Ihren Anforderungen in Bezug auf Skripts und Ihren individuellen Sicherheitszielen Rechnung zu tragen. Das bedeutet nicht, dass Windows PowerShell den Benutzern die Ausführung von Skripts unmöglich macht. Vielmehr erschwert sie es den Benutzern, Skripts auszuführen, ohne dass Sie sich dessen bewusst sind. Ausführliche Informationen finden Sie unter Windows PowerShell Script Security in [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145) .

</div>

<span> </span>

</div>

</div>

</div>

