---
title: 'Lync Server 2013: von der Ankündigungsanwendung verwendete Komponenten'
description: 'Lync Server 2013: von der Ankündigungsanwendung verwendete Komponenten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5338ad097c814d5c6435bd89dbf7cfa8680feb8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577691"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a>Von der Ankündigungsanwendung in lync Server 2013 verwendete Komponenten

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-13_

In lync Server 2013 ist der Ankündigungsanwendung eine Komponente der Reaktionsgruppenanwendung. Wenn Sie Enterprise-VoIP bereitstellen, wird der Ankündigungsanwendung automatisch zusammen mit dem Reaktionsgruppenanwendung installiert und aktiviert. In diesem Abschnitt werden die Komponenten beschrieben, die den Ankündigungsanwendung unterstützen.

<div>

## <a name="announcement-application-components"></a>Komponenten der Ankündigungsanwendung

Die folgenden lync Server Komponenten unterstützen das Ankündigungsanwendung:

  - **Anwendungsdienst**     Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen. Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.

  - **Reaktionsgruppenanwendung**     Die Reaktionsgruppenanwendung ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden. Wenn ein nicht zugewiesener Telefonnummern Bereich für die Weiterleitung an eine Ansage konfiguriert ist, muss der Reaktionsgruppenanwendung die Anrufe an die Telefonnummer weiterleiten. (Reaktionsgruppenanwendung ist nicht erforderlich, wenn alle Bereiche für die Weiterleitung an Exchange Unified Messaging (um) konfiguriert sind.)

  - **Audio-Dateien**     Audio-Dateien werden für die Ankündigungen verwendet.

  - **Dateispeicher**     Der Ankündigungsanwendung verwendet Dateispeicher, um seine Audiodateien zu speichern.

  - **Lync Server-Systemsteuerung**     Sie können lync Server-Systemsteuerung verwenden, um die Tabelle nicht zugewiesener Nummern zu konfigurieren.

  - **Lync Server-Verwaltungsshell**     Sie können lync Server-Verwaltungsshell-Cmdlets zum Konfigurieren von Ankündigungseinstellungen und der Tabelle nicht zugewiesener Nummern verwenden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

