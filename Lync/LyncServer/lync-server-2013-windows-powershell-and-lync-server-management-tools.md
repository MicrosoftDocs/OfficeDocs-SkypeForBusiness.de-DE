---
title: 'Lync Server 2013: Windows PowerShell und Lync Server-Verwaltungstools'
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
ms.openlocfilehash: dbfd15ff3c1047f04a6878b65a3d16e63bac490b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a>Windows PowerShell und Lync Server 2013-Verwaltungstools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-07-20_

In Microsoft lync Server 2013 werden Verwaltungstools mithilfe von Windows PowerShell implementiert. Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache. Zu den lync Server 2013-Tools, die mit Windows PowerShell implementiert werden, gehören die folgenden:

  - **Topologie-Generator** Sie verwenden den Topologie-Generator zum Erstellen, anpassen und Veröffentlichen Ihrer geplanten Topologie, und Sie überprüft Ihre Topologie, bevor Sie mit Server Installationen beginnen. Wenn Sie lync Server 2013 auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server gemäß den Anweisungen in der Topologie bereit. Nach dem Setup werden die Konfigurationsinformationen automatisch auf alle Server repliziert. Komponenten können Ihrer Bereitstellung nur mithilfe des Topologie-Generators hinzugefügt werden.

  - **Lync Server-Verwaltungsshell**. Sie können die lync Server-Verwaltungsshell für die vollständige Befehlszeilenverwaltung Ihrer Bereitstellung verwenden.

  - **Lync Server-System**Steuerung. Sie können die Benutzeroberfläche der Microsoft lync Server 2013-Systemsteuerung verwenden, um die am häufigsten ausgeführten Aufgaben in Ihrer Bereitstellung zu verwalten.

Diese Tools verwenden Windows PowerShell-Cmdlets für die Verwaltung Ihrer Bereitstellung, einschließlich in der Nähe von 550-produktspezifischen Cmdlets. Die in lync Server 2013 enthaltenen Sicherheits-Cmdlets werden in erster Linie zum Verwalten der Authentifizierung und von Benutzerrechten und-Berechtigungen verwendet. Zum Verwalten der Authentifizierung stehen vielfältige Cmdlets zur Verfügung, darunter Cmdlets für die Zertifikat- und PIN-Authentifizierung. Darüber hinaus können Sie mithilfe einer Reihe von Cmdlets das neue Feature für die rollenbasierte Zugriffssteuerung verwenden, um die administrative Steuerung von lync Server 2013 zu delegieren. Details zu den lync Server-Cmdlets finden Sie unter [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

Die Skript Sicherheitsfeatures für Windows PowerShell wurden speziell entwickelt, um zu verhindern, dass einige der Skript bezogenen Sicherheitsprobleme älterer Technologien, einschließlich Microsoft Visual Basic Scripting Edition (VBScript), unterstützt werden. Die Windows PowerShell-Sicherheitsfeatures sollen eine Umgebung erstellen, in der Benutzer keine einfachen oder unwissentlichen Skripts ausführen können. Standardmäßig sind die Windows PowerShell-Sicherheitsfeatures aktiviert. Sie können den Zustand dieser Features ändern, damit Sie Ihren Skriptanforderungen und einer Reihe von Sicherheitszielen gerecht werden. Dies soll nicht heißen, dass die Shell es Benutzern unmöglich macht, Skripts auszuführen. Stattdessen erschwert die Shell standardmäßig, dass Benutzer Skripts ausführen können, ohne dass dies zu erkennen ist. Ausführliche Informationen finden Sie unter Windows PowerShell-Skript [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)Sicherheit unter.

</div>

<span> </span>

</div>

</div>

</div>

