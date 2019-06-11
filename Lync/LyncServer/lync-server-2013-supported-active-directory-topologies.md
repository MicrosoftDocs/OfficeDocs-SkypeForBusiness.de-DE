---
title: 'Lync Server 2013: Unterstützte Active Directory-Topologien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Unterstützte Active Directory-Topologien in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-10-02_

Lync Server 2013 unterstützt dieselben Active Directory-Domänendienste-Topologien wie Microsoft lync Server 2010 und Microsoft Office Communications Server 2007 R2. Die folgenden Topologien werden unterstützt:

  - Einzelne Gesamtstruktur mit einzelner Domäne

  - Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

  - Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

  - Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

  - Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur

  - Mehrere Gesamtstrukturen in einer lync-Ressourcengesamtstruktur-Topologie mit Exchange Online

In der folgenden Abbildung sind die Symbole aufgeführt, die in den Illustrationen in diesem Abschnitt verwendet werden.

**Schlüssel zu Topologie-Illustrationen**

![Schlüssel zu Topologie] -Illustrationen (images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Schlüssel zu Topologie") -Illustrationen

<div>

## <a name="single-forest-single-domain"></a>Einzelne Gesamtstruktur, einzelne Domäne

Die einfachste Active Directory-Topologie, die von lync Server, einer einzelnen Domänengesamtstruktur, unterstützt wird, ist eine allgemeine Topologie.

Die folgende Abbildung zeigt eine lync Server-Bereitstellung in einer einzelnen Active Directory-Domänentopologie.

**Topologie mit einer einzelnen Domäne**

![Topologie einer einzelnen Domäne] (images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologie einer einzelnen Domäne")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>Einzelne Gesamtstruktur, mehrere Domänen

Eine andere von lync Server unterstützte Active Directory-Topologie ist eine einzelne Gesamtstruktur, die aus einer Stammdomäne und einer oder mehreren untergeordneten Domänen besteht. Bei dieser Art von Active Directory-Topologie kann sich die Domäne, in der Sie Benutzer erstellen, von der Domäne unterscheiden, in der Sie lync Server bereitstellen. Wenn Sie jedoch einen Front-End-Pool bereitstellen, müssen Sie alle Front-End-Server im Pool innerhalb einer einzigen Domäne bereitstellen. Die lync Server-Unterstützung für universelle Windows-Administratorgruppen ermöglicht die domänenübergreifende Verwaltung.

Die folgende Abbildung zeigt eine Bereitstellung in einer einzelnen Gesamtstruktur mit mehreren Domänen. In dieser Abbildung zeigt ein Benutzersymbol die Domäne an, in der sich das Benutzerkonto befindet, und der Pfeil verweist auf die Domäne, in der sich der lync-Server Pool befindet. Zu den Benutzerkonten gehören die folgenden:

  - Benutzerkonten innerhalb der gleichen Domäne wie der lync-Server Pool

  - Benutzerkonten in einer anderen Domäne als dem lync-Server Pool

  - Benutzerkonten in einer untergeordneten Domäne der Domäne mit dem lync-Server Pool

**Einzelne Gesamtstruktur mit mehreren Domänen**

![Einzelne Gesamtstruktur mit mehreren Domänen] (images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Einzelne Gesamtstruktur mit mehreren Domänen")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>Einzelne Gesamtstruktur, mehrere Strukturen

Eine Topologie mit mehreren Strukturen besteht aus zwei oder mehr Domänen, die unabhängige Struktur Strukturen und separate Active Directory-Namespaces definieren.

Die folgende Abbildung zeigt eine einzelne Gesamtstruktur mit mehreren Strukturen. In dieser Abbildung zeigt ein Benutzersymbol die Domäne an, in der sich das Benutzerkonto befindet, eine durchgezogene Linie verweist auf einen lync-Serverpool, der sich in derselben oder einer anderen Domäne befindet, und eine gestrichelte Linie verweist auf den lync-Serverpool, der sich in einer anderen Struktur befindet. Zu den Benutzerkonten gehören die folgenden:

  - Benutzerkonten innerhalb der gleichen Domäne wie der lync-Server Pool

  - Benutzerkonten in einer anderen Domäne als der lync-Server Pool (aber dieselbe Struktur wie)

  - Benutzerkonten in einer anderen Struktur aus dem lync-Server Pool

**Einzelne Gesamtstruktur mit mehreren Strukturen**

![Einzelne Gesamtstruktur mit mehreren Strukturen] (images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Einzelne Gesamtstruktur mit mehreren Strukturen")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>Mehrere Gesamtstrukturen, zentrale Gesamtstruktur

Lync Server unterstützt mehrere Gesamtstrukturen, die in einer zentralen Gesamtstrukturtopologie konfiguriert sind. Zentrale Gesamtstruktur Topologien verwenden Kontaktobjekte in der zentralen Gesamtstruktur, um Benutzer in den anderen Gesamtstrukturen darzustellen. Die zentrale Gesamtstruktur hostet auch Benutzerkonten für alle Benutzer in dieser Gesamtstruktur. Ein Verzeichnis Synchronisierungs Produkt wie Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1) verwaltet den Lebenszyklus von Benutzerkonten innerhalb die Organisation: Wenn ein neues Benutzerkonto in einer der Gesamtstrukturen erstellt oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Verzeichnis Synchronisierungs Produkt den entsprechenden Kontakt in der zentralen Gesamtstruktur.

Eine zentrale Gesamtstruktur bietet die folgenden Vorteile:

  - Server mit lync Server werden innerhalb einer einzigen Gesamtstruktur zentralisiert.

  - Benutzer können in jeder Gesamtstruktur nach anderen Benutzern suchen und mit Ihnen kommunizieren.

  - Benutzer können die Anwesenheit anderer Benutzer in einer beliebigen Gesamtstruktur anzeigen.

  - Das Verzeichnis Synchronisierungs Produkt automatisiert das Hinzufügen und Löschen von Kontaktobjekten in der zentralen Gesamtstruktur, wenn Benutzerkonten erstellt oder entfernt werden.

Die folgende Abbildung veranschaulicht eine zentrale Gesamtstrukturtopologie. In dieser Abbildung gibt es bidirektionale Vertrauensstellungen zwischen der Domäne, die lync Server hostet, die sich in der zentralen Gesamtstruktur befindet, und jeder Benutzerdomäne, die sich in einer separaten Gesamtstruktur befindet. Das Schema in den separaten Benutzergesamtstrukturen muss nicht erweitert werden.

**Zentrale Gesamtstrukturtopologie**

![Zentrale Gesamtstrukturtopologie] (images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Zentrale Gesamtstrukturtopologie")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>Mehrere Gesamtstrukturen, Ressourcengesamtstruktur

In einer Ressourcengesamtstruktur-Topologie ist eine Gesamtstruktur für die Ausführung von Serveranwendungen wie Microsoft Exchange Server und lync Server reserviert. Die Ressourcengesamtstruktur hostet die Serveranwendungen und eine synchronisierte Darstellung des aktiven Benutzerobjekts, enthält jedoch keine Anmelde fähigen Benutzerkonten. Die Ressourcengesamtstruktur fungiert als Umgebung für gemeinsame Dienste für die anderen Gesamtstrukturen, in denen sich Benutzerobjekte befinden. Die Benutzergesamtstrukturen verfügen über eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur. Wenn Sie lync Server in dieser Art von Topologie bereitstellen, erstellen Sie für jedes Benutzerkonto in den Benutzergesamtstrukturen ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur. Wenn Microsoft Exchange bereits in der Ressourcengesamtstruktur bereitgestellt wurde, sind die deaktivierten Benutzerkonten möglicherweise bereits vorhanden. Ein Verzeichnis Synchronisierungs Produkt wie MIIS, Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1) verwaltet den Lebenszyklus von Benutzerkonten. Wenn ein neues Benutzerkonto in einer der Benutzergesamtstrukturen erstellt oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Verzeichnis Synchronisierungs Produkt die entsprechende Benutzerdarstellung in der Ressourcengesamtstruktur.

Diese Topologie kann verwendet werden, um eine gemeinsame Infrastruktur für Dienste in Organisationen bereitzustellen, die mehrere Gesamtstrukturen verwalten, oder um die Verwaltung von Active Directory-Objekten von anderer Verwaltung zu trennen. Unternehmen, die die Active Directory-Verwaltung aus Sicherheitsgründen isolieren müssen, wählen diese Topologie häufig aus.

Diese Topologie bietet den Vorteil, dass die Erweiterung des Active Directory-Schemas auf eine einzelne Gesamtstruktur (also die Ressourcengesamtstruktur) eingeschränkt werden muss.

Das folgende Diagramm veranschaulicht eine Ressourcengesamtstruktur-Topologie.

**Topologie der Ressourcengesamtstruktur**

![Topologie der Active Directory-Ressourcengesamtstruktur] (images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologie der Active Directory-Ressourcengesamtstruktur")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer lync-Ressourcengesamtstruktur-Topologie mit Exchange Online

In dieser Topologie befinden sich eine oder mehrere Gesamtstrukturen lokal und sind für das Hosten von Active Directory-Benutzerkonten reserviert. Die Ressourcengesamtstruktur befindet sich außerhalb des Lokals und wird von einem externen Hostinganbieter verwaltet. Die Ressourcengesamtstruktur enthält nur die lync Server-Bereitstellung und eine synchronisierte Replikation der Benutzerkonten aus der lokalen Benutzerkontengesamtstruktur (en). Sie enthält keine Anmelde fähigen Benutzerkonten. Exchange wird entweder in der lokalen Benutzerkonten-Gesamtstruktur (en) bereitgestellt, die zusammen mit Exchange Online (Hybrid) integriert ist, oder e-Mail-Dienste für die lokalen Benutzerkonten werden ausschließlich von Exchange Online bereitgestellt.

Die Ressourcengesamtstruktur fungiert als Umgebung für gemeinsame Dienste für die lokalen Active Directory-Gesamtstrukturen, in denen sich Benutzerobjekte befinden. Die Gesamtstruktur des Benutzerkontos verfügt über eine unidirektionale Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur. Wenn Sie lync Server in dieser Art von Topologie bereitstellen, erstellen Sie für jedes Benutzerkonto in den Benutzergesamtstrukturen ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur. Ein Verzeichnis Synchronisierungs Produkt wie MIIS, Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1) verwaltet den Lebenszyklus von Benutzerkonten. Wenn ein neues Benutzerkonto in einer der Benutzergesamtstrukturen erstellt oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Verzeichnis Synchronisierungs Produkt die entsprechende Benutzerdarstellung in der Ressourcengesamtstruktur. Weitere Informationen zum Konfigurieren einer Bereitstellung mit mehreren Gesamtstrukturen finden Sie unter [Bereitstellen von lync in einer Architektur mit mehreren Gesamtstrukturen (Partner Hosted lync mit Exchange-Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).

</div>

</div>

<span> </span>

</div>

</div>

</div>

