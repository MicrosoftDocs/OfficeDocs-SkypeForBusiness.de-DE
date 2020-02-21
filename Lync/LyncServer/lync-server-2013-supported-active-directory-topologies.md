---
title: 'Lync Server 2013: Unterstützte Active Directory-Topologien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9437df126889aefb8400b50d118d44dac12f285d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Unterstützte Active Directory Topologien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-10-02_

Lync Server 2013 unterstützt dieselben Active Directory-Domänendienste Topologien wie Microsoft lync Server 2010 und Microsoft Office Communications Server 2007 R2. Folgende Topologien werden unterstützt:

  - Einzelne Gesamtstruktur mit einzelner Domäne

  - Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

  - Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

  - Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

  - Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur

  - Mehrere Gesamtstrukturen in einer lync-Ressourcengesamtstruktur-Topologie mit Exchange Online

Nachfolgend werden die in den Abbildungen in diesem Abschnitt verwendeten Symbole erläutert.

**Legende zu den Topologieabbildungen**

![Legende zu den Topologieabbildungen](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Legende zu den Topologieabbildungen")

<div>

## <a name="single-forest-single-domain"></a>Einzelne Gesamtstruktur, einzelne Domäne

Die einfachste Active Directory Topologie, die von lync Server, einer einzelnen Domänengesamtstruktur, unterstützt wird, ist eine allgemeine Topologie.

In der folgenden Abbildung wird eine lync Server-Bereitstellung in einer einzelnen Domäne Active Directory Topologie veranschaulicht.

**Topologie mit einer einzelnen Domäne**

![Topologie mit einer einzelnen Domäne](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologie mit einer einzelnen Domäne")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>Einzelne Gesamtstruktur, mehrere Domänen

Eine andere Active Directory Topologie, die von lync Server unterstützt wird, ist eine einzelne Gesamtstruktur, die aus einer Stammdomäne und einer oder mehreren untergeordneten Domänen besteht. Bei dieser Art von Active Directory Topologie kann die Domäne, in der Sie Benutzer erstellen, sich von der Domäne unterscheiden, in der Sie lync Server bereitstellen. Wenn Sie jedoch einen Front-End-Pool bereitstellen, müssen Sie alle Front-End-Server im Pool innerhalb einer einzelnen Domäne bereitstellen. Lync Server-Unterstützung für Windows universelle Administratorgruppen ermöglicht die domänenübergreifende Verwaltung.

Die folgende Abbildung zeigt eine Bereitstellung in einer einzelnen Gesamtstruktur mit mehreren Domänen. In dieser Abbildung zeigt ein Benutzersymbol die Domäne an, in der das Benutzerkonto verwaltet wird, und der Pfeil verweist auf die Domäne, in der sich der lync Server Pool befindet. Es gibt folgende Benutzerkonten:

  - Benutzerkonten in derselben Domäne wie der lync Server Pool

  - Benutzerkonten in einer anderen Domäne als der lync Server Pool

  - Benutzerkonten in einer untergeordneten Domäne der Domäne mit dem lync Server Pool

**Einzelne Gesamtstruktur mit mehreren Domänen**

![Einzelne Gesamtstruktur mit mehreren Domänen](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Einzelne Gesamtstruktur mit mehreren Domänen")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>Einzelne Gesamtstruktur, mehrere Strukturen

Eine Gesamtstruktur mit mehreren Strukturen besteht aus zwei oder mehr Domänen, die unabhängige Strukturen und separate Active Directory-Namespaces definieren.

In der folgenden Abbildung ist eine einzelne Gesamtstruktur mit mehreren Strukturen dargestellt. In dieser Abbildung zeigt ein Benutzersymbol die Domäne, in der das Benutzerkonto verwaltet wird, eine durchgehende Linie verweist auf einen lync Server Pool, der sich in derselben oder einer anderen Domäne befindet, und eine gestrichelte Linie verweist auf lync Server Pool, der sich in einer anderen Struktur befindet. Es gibt folgende Benutzerkonten:

  - Benutzerkonten in derselben Domäne wie der lync Server Pool

  - Benutzerkonten in einer anderen Domäne als der lync Server Pool (jedoch dieselbe Struktur wie)

  - Benutzerkonten in einer anderen Struktur als der lync Server Pool

**Einzelne Gesamtstruktur mit mehreren Strukturen**

![Einzelne Gesamtstruktur mit mehreren Strukturen](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Einzelne Gesamtstruktur mit mehreren Strukturen")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>Mehrere Gesamtstrukturen, zentrale Gesamtstruktur

Lync Server unterstützt mehrere Gesamtstrukturen, die in einer Topologie mit zentraler Gesamtstruktur konfiguriert sind. In Topologien mit zentraler Gesamtstruktur werden Kontaktobjekte in der zentralen Gesamtstruktur dazu verwendet, Benutzer in den anderen Gesamtstrukturen darzustellen. In der zentralen Gesamtstruktur werden auch die Benutzerkonten von anderen Benutzern in dieser Gesamtstruktur gehostet. Ein Produkt zur Verzeichnissynchronisierung, wie z. B. Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus von Benutzerkonten innerhalb Ihrer Organisation: Wenn ein neues Benutzerkonto in einer der Gesamtstrukturen erstellt wird oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Programm zur Verzeichnissynchronisierung den entsprechenden Kontakt in der zentralen Gesamtstruktur.

Eine zentrale Gesamtstruktur bietet die folgenden Vorteile:

  - Server mit lync Server werden in einer einzelnen Gesamtstruktur zentralisiert.

  - Benutzer können nach anderen Benutzern in einer beliebigen Gesamtstruktur suchen oder mit ihnen kommunizieren.

  - Benutzer können Anwesenheitsinformationen zu anderen Benutzern in einer beliebigen Gesamtstruktur anzeigen.

  - Das Produkt zur Verzeichnissynchronisierung automatisiert das Hinzufügen und Löschen von Kontaktobjekten in der zentralen Gesamtstruktur, wenn Benutzerkonten erstellt oder entfernt werden.

Die folgende Abbildung zeigt eine Topologie mit zentraler Gesamtstruktur. In dieser Abbildung gibt es bidirektionale Vertrauensstellungen zwischen der Domäne, die lync Server hostet, der sich in der zentralen Gesamtstruktur befindet, und jeder Benutzerdomäne, die sich in einer separaten Gesamtstruktur befindet. Das Schema in den separaten Benutzergesamtstrukturen muss nicht erweitert werden.

**Topologie mit einer zentralen Gesamtstruktur**

![Topologie mit einer zentralen Gesamtstruktur](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologie mit einer zentralen Gesamtstruktur")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>Mehrere Gesamtstrukturen, Ressourcengesamtstruktur

In einer Topologie mit Ressourcengesamtstruktur ist eine Gesamtstruktur für die Ausführung von Serveranwendungen dediziert, beispielsweise Exchange Server und lync Server. Die Ressourcengesamtstruktur hostet die Serveranwendungen sowie eine synchronisierte Darstellung des aktiven Benutzerobjekts, enthält jedoch keine für die Anmeldung aktivierten Benutzerkonten. Die Ressourcengesamtstruktur fungiert als Umgebung für freigegebene Dienste für die weiteren Gesamtstrukturen, in denen sich Benutzerobjekte befinden. Zwischen den Benutzergesamtstrukturen und der Ressourcengesamtstruktur besteht eine Vertrauensstellung auf Gesamtstrukturebene. Wenn Sie lync Server in dieser Art von Topologie bereitstellen, erstellen Sie ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen. Wenn Microsoft Exchange bereits in der Ressourcengesamtstruktur bereitgestellt wurde, sind die deaktivierten Benutzerkonten möglicherweise bereits vorhanden. Ein Produkt zur Verzeichnissynchronisierung, wie z. B. Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus von Benutzerkonten innerhalb Ihrer Organisation. Wenn ein neues Benutzerkonto in einer der Benutzerstrukturen erstellt wird oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Programm zur Verzeichnissynchronisierung das entsprechende Benutzerobjekt in der Ressourcengesamtstruktur.

Diese Topologie kann verwendet werden, um eine freigegebene Infrastruktur für Dienste in Organisationen bereitzustellen, in denen mehrere Gesamtstrukturen verwaltet werden, oder um die Verwaltung von Active Directory-Objekten von anderen Verwaltungsaufgaben zu trennen. Diese Topologie wird häufig von Unternehmen eingesetzt, die die Active Directory-Verwaltung aus Sicherheitsgründen isolieren müssen.

Diese Topologie bietet den Vorteil, dass das Active Directory-Schema lediglich in einer einzelnen Gesamtstruktur (der Ressourcengesamtstruktur) erweitert werden muss.

Die folgende Abbildung zeigt eine Topologie mit Ressourcengesamtstruktur.

**Ressourcengesamtstruktur-Topologie**

![Active Directory Topologie der Ressourcengesamtstruktur](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Topologie der Ressourcengesamtstruktur")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer lync-Ressourcengesamtstruktur-Topologie mit Exchange Online

In dieser Topologie befinden sich eine oder mehrere Gesamtstrukturen lokal und sind dem Hosten Active Directory Benutzerkonten gewidmet. Die Ressourcengesamtstruktur befindet sich außerhalb des Standorts und wird von einem Drittanbieter-Hostinganbieter verwaltet. Die Ressourcengesamtstruktur enthält nur die lync Server-Bereitstellung und eine synchronisierte Replikation der Benutzerkonten aus der lokalen Benutzerkonten-Gesamtstruktur (en). Sie enthält keine Anmelde aktivierten Benutzerkonten. Exchange wird entweder in den lokalen Benutzerkonten-Gesamtstrukturen bereitgestellt, die zusammen mit Exchange Online (Hybrid) integriert sind, oder e-Mail-Dienste für die lokalen Benutzerkonten werden ausschließlich von Exchange Online bereitgestellt.

Die Ressourcengesamtstruktur fungiert als Umgebung für gemeinsame Dienste für die lokalen Active Directory Gesamtstruktur (en), in der sich Benutzerobjekte befinden. Die Benutzerkontengesamtstruktur (en) haben eine unidirektionale Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur. Wenn Sie lync Server in dieser Art von Topologie bereitstellen, erstellen Sie ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen. Ein Produkt zur Verzeichnissynchronisierung, wie z. B. Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus von Benutzerkonten innerhalb Ihrer Organisation. Wenn ein neues Benutzerkonto in einer der Benutzerstrukturen erstellt wird oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Programm zur Verzeichnissynchronisierung das entsprechende Benutzerobjekt in der Ressourcengesamtstruktur. Weitere Informationen zum Konfigurieren einer Bereitstellung mit mehreren Gesamtstrukturen finden Sie unter [Deploying lync in a Multi-Forest Architecture (Partner Hosted lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).

</div>

</div>

<span> </span>

</div>

</div>

</div>

