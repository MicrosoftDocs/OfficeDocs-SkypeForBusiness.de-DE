---
title: 'Lync Server 2013: Bereitstellen von lync-Clients'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 351fc1b62f0ef72cb3580f3c5d43dc8486799aec
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>Bereitstellen von lync-Clients in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

In lync 2013 wird ein anderer Ansatz für die Clientbereitstellung eingeführt. Bei einer Abweichung aus früheren Versionen verfügt lync 2013 nicht mehr über ein eigenes Installationsprogramm. Stattdessen ist lync im Office 2013-Setupprogramm enthalten. Um lync 2013 für Ihre Benutzer bereitzustellen, können Sie Office 2013 Installationsmethoden und Anpassungstools verwenden.

  - **Office 2013 Windows Installer** ist ein Windows Installer-basiertes Installationspaket, das aus mehreren MSI-Dateien besteht. Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert. Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus. In den Themen in diesem Abschnitt wird beschrieben, wie Sie die Office 2013 Windows Installer verwenden und anpassen, um lync 2013 bereitzustellen.

  - **Office 2013 Klick-und-Los** ist ein Installationsprogramm, das die Office-Setupdateien aus dem Microsoft Office 365-Portal an den Benutzer streamt. Administratoren können die Installation mithilfe des Office-Bereitstellungstools für Klick-und-Los anpassen. Da Office 2013 Klick-und-Los in erster Linie in der Microsoft Office 365-Umgebung verwendet wird, wird diese Installationsmethode in diesem Abschnitt nicht ausführlich beschrieben. Ausführliche Informationen zur Verwendung und Anpassung der Klick-und-Los-Installation finden Sie in der Dokumentation zum Office 2013 Resource Kit. Administratoren können auch die Office 2013 Klick-und-Los-Programm-und sprach Quelldateien an einen lokalen Speicherort herunterladen, was nützlich ist, wenn Sie die Netzwerk Nachfrage minimieren oder verhindern möchten, dass Benutzer Software aus dem Internet installieren, weil Sicherheitsanforderungen für Unternehmen.

Die Themen in diesem Abschnitt konzentrieren sich auf die Bereitstellung von Clients mithilfe des Office 2013 MSI-basierten Installationsprogramms. Ihr primärer Verweis sollte die Office 2013 Resource Kit-Dokumentation sein, in der ausführlich erläutert wird, wie Sie Ihre Infrastruktur vorbereiten, Setup anpassen und Office 2013 bereitstellen. Sie sollten jedoch die Office-Dokumentation in Verbindung mit Themen in diesem Abschnitt verwenden, die auf Bereitstellungsüberlegungen hinweisen, die spezifisch für lync 2013 sind.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Das Online Besprechungs-Add-in für lync 2013, das die Besprechungsverwaltung im Outlook-Client für Messaging und Zusammenarbeit unterstützt, wird automatisch mit lync 2013 installiert.</P>
> <LI>
> <P>Mit dem Setupprogramm für Office 2013 werden frühere Versionen von lync oder Office Communicator nicht deinstalliert. Der lync 2013 Client wird nebeneinander mit anderen lync-oder Office Communicator-Clients installiert.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Anpassen der Clientinstallation in lync Server 2013](lync-server-2013-customizing-client-installation.md)

  - [Anpassen von lync-Verhalten und der Benutzeroberfläche in lync Server 2013](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [Anpassen des Online Besprechungs-Add-Ins in lync Server 2013](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [Konfigurieren der Seite für den besprechungsbeitritt in lync Server 2013](lync-server-2013-configuring-the-meeting-join-page.md)

  - [Konfigurieren unterstützter Clientversionen in lync Server 2013](lync-server-2013-configuring-supported-client-versions.md)

  - [Konfigurieren des Datenschutzmodus für erweiterte Anwesenheitsinformationen in lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

