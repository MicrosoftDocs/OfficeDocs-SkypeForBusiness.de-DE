---
title: 'Lync Server 2013: Unterstützte Active Directory-Topologien'
TOCTitle: Unterstützte Active Directory-Topologien
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398173(v=OCS.15)
ms:contentKeyID: 49293154
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Active Directory-Topologien in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 unterstützt dieselben Active Directory-Domänendienste-Topologien wie Microsoft Lync Server 2010 und Microsoft Office Communications Server 2007 R2. Folgende Topologien werden unterstützt:

  - Einzelne Gesamtstruktur mit einzelner Domäne

  - Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

  - Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

  - Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

  - Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur

  - Mehrere Gesamtstrukturen in einer Lync-Ressourcengesamtstruktur-Topologie mit Exchange Online

Nachfolgend werden die in den Abbildungen in diesem Abschnitt verwendeten Symbole erläutert.

**Legende zu den Topologieabbildungen**

![Legende zu den Topologieabbildungen](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Legende zu den Topologieabbildungen")

## Einzelne Gesamtstruktur, einzelne Domäne

Die einfachste der von Lync Server unterstützten Active Directory-Topologien, eine Gesamtstruktur mit einer einzelnen Domäne, ist eine häufig verwendete Topologie.

In der folgenden Abbildung ist eine Lync Server-Bereitstellung in einer Active Directory-Topologie mit einer einzelnen Domäne dargestellt.

**Topologie mit einer einzelnen Domäne**

![Topologie mit einer einzelnen Domäne](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologie mit einer einzelnen Domäne")

## Einzelne Gesamtstruktur, mehrere Domänen

Eine weitere von Lync Server unterstützte Active Directory-Topologie besteht aus einer einzelnen Gesamtstruktur mit einer Stammdomäne und einer oder mehreren untergeordneten Domänen. Bei dieser Art von Active Directory-Topologie kann sich die Domäne, in der Sie Benutzer erstellen, von der Domäne unterscheiden, in der Sie Lync Server bereitstellen. Wenn Sie jedoch einen Front-End-Pool bereitstellen, müssen Sie alle Front-End-Server im Pool innerhalb einer einzelnen Domäne bereitstellen. Die Lync Server-Unterstützung von universellen Windows-Administratorgruppen ermöglicht eine domänenübergreifende Verwaltung.

Die folgende Abbildung zeigt eine Bereitstellung in einer einzelnen Gesamtstruktur mit mehreren Domänen. In dieser Abbildung kennzeichnet ein Benutzersymbol die Domäne, in der das Benutzerkonto verwaltet wird, und der Pfeil verweist auf die Domäne, in der sich der Lync Server-Pool befindet. Es gibt folgende Benutzerkonten:

  - Benutzerkonten innerhalb derselben Domäne wie der Lync Server-Pool

  - Benutzerkonten in einer anderen Domäne als der Lync Server-Pool

  - Benutzerkonten in einer untergeordneten Domäne der Domäne mit dem Lync Server-Pool

**Einzelne Gesamtstruktur mit mehreren Domänen**

![Einzelne Gesamtstruktur mit mehreren Domänen](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Einzelne Gesamtstruktur mit mehreren Domänen")

## Einzelne Gesamtstruktur, mehrere Strukturen

Eine Gesamtstruktur mit mehreren Strukturen besteht aus zwei oder mehr Domänen, die unabhängige Strukturen und separate Active Directory-Namespaces definieren.

In der folgenden Abbildung wird eine einzelne Gesamtstruktur mit mehreren Strukturen veranschaulicht. In dieser Abbildung kennzeichnet ein Benutzersymbol die Domäne, in der das Benutzerkonto verwaltet wird. Eine durchgezogene Linie zeigt auf den Lync Server-Pool, der sich in derselben oder einer anderen Domäne befindet, und eine gestrichelte Linie zeigt auf einen Lync Server-Pool, der sich in einer anderen Struktur befindet. Es gibt folgende Benutzerkonten:

  - Benutzerkonten innerhalb derselben Domäne wie der Lync Server-Pool

  - Benutzerkonten in einer anderen Domäne als der Lync Server-Pool (aber in derselben Struktur)

  - Benutzerkonten in einer anderen Struktur als der Lync Server-Pool

**Einzelne Gesamtstruktur mit mehreren Strukturen**

![Einzelne Gesamtstruktur mit mehreren Strukturen](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Einzelne Gesamtstruktur mit mehreren Strukturen")

## Mehrere Gesamtstrukturen, zentrale Gesamtstruktur

Lync Server unterstützt mehrere Gesamtstrukturen, die in einer Topologie mit zentraler Gesamtstruktur konfiguriert sind. In Topologien mit zentraler Gesamtstruktur werden Kontaktobjekte in der zentralen Gesamtstruktur dazu verwendet, Benutzer in den anderen Gesamtstrukturen darzustellen. In der zentralen Gesamtstruktur werden auch die Benutzerkonten von anderen Benutzern in dieser Gesamtstruktur gehostet. Ein Produkt zur Verzeichnissynchronisierung, wie z. B. Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus von Benutzerkonten innerhalb Ihrer Organisation: Wenn ein neues Benutzerkonto in einer der Gesamtstrukturen erstellt wird oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Programm zur Verzeichnissynchronisierung den entsprechenden Kontakt in der zentralen Gesamtstruktur.

Eine zentrale Gesamtstruktur bietet die folgenden Vorteile:

  - Server mit Lync Server werden in einer einzelnen Gesamtstruktur zentralisiert.

  - Benutzer können nach anderen Benutzern in einer beliebigen Gesamtstruktur suchen oder mit ihnen kommunizieren.

  - Benutzer können Anwesenheitsinformationen zu anderen Benutzern in einer beliebigen Gesamtstruktur anzeigen.

  - Das Produkt zur Verzeichnissynchronisierung automatisiert das Hinzufügen und Löschen von Kontaktobjekten in der zentralen Gesamtstruktur, wenn Benutzerkonten erstellt oder entfernt werden.

Die folgende Abbildung zeigt eine Topologie mit zentraler Gesamtstruktur. In dieser Abbildung gibt es bidirektionale Vertrauensstellungen zwischen der Domäne, in der Lync Server gehostet wird (die zentrale Gesamtstruktur), und den einzelnen Domänen nur für Benutzer, die sich in einer separaten Gesamtstruktur befinden. Das Schema in den separaten Benutzergesamtstrukturen muss nicht erweitert werden.

**Topologie mit einer zentralen Gesamtstruktur**

![Topologie mit einer zentralen Gesamtstruktur](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologie mit einer zentralen Gesamtstruktur")

## Mehrere Gesamtstrukturen, Ressourcengesamtstruktur

In einer Topologie mit Ressourcengesamtstruktur wird eine Gesamtstruktur ausgeführten Serveranwendungen, z. B. Microsoft Exchange Server und Lync Server, zugeordnet. Die Ressourcengesamtstruktur hostet die Serveranwendungen sowie eine synchronisierte Darstellung des aktiven Benutzerobjekts, enthält jedoch keine für die Anmeldung aktivierten Benutzerkonten. Die Ressourcengesamtstruktur fungiert als Umgebung für freigegebene Dienste für die weiteren Gesamtstrukturen, in denen sich Benutzerobjekte befinden. Zwischen den Benutzergesamtstrukturen und der Ressourcengesamtstruktur besteht eine Vertrauensstellung auf Gesamtstrukturebene. Wenn Sie Lync Server in dieser Art von Topologie bereitstellen, erstellen Sie für jedes Benutzerkonto in den Benutzergesamtstrukturen ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur. Wenn Microsoft Exchange bereits in der Ressourcengesamtstruktur bereitgestellt wurde, sind die deaktivierten Benutzerkonten möglicherweise bereits vorhanden. Ein Produkt zur Verzeichnissynchronisierung, wie z. B. Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus von Benutzerkonten innerhalb Ihrer Organisation. Wenn ein neues Benutzerkonto in einer der Benutzerstrukturen erstellt wird oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Programm zur Verzeichnissynchronisierung das entsprechende Benutzerobjekt in der Ressourcengesamtstruktur.

Diese Topologie kann verwendet werden, um eine freigegebene Infrastruktur für Dienste in Organisationen bereitzustellen, in denen mehrere Gesamtstrukturen verwaltet werden, oder um die Verwaltung von Active Directory-Objekten von anderen Verwaltungsaufgaben zu trennen. Diese Topologie wird häufig von Unternehmen eingesetzt, die die Active Directory-Verwaltung aus Sicherheitsgründen isolieren müssen.

Diese Topologie bietet den Vorteil, dass das Active Directory-Schema lediglich in einer einzelnen Gesamtstruktur (der Ressourcengesamtstruktur) erweitert werden muss.

Die folgende Abbildung zeigt eine Topologie mit Ressourcengesamtstruktur.

**Topologie mit Ressourcengesamtstruktur**

![Active Directory: Topologie mit einer Ressourcengesamtstruktur](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory: Topologie mit einer Ressourcengesamtstruktur")

## Mehrere Gesamtstrukturen in einer Lync-Ressourcengesamtstruktur-Topologie mit Exchange Online

In dieser Topologie befinden sich eine oder mehrere lokale Gesamtstrukturen, die für das Hosten von Active Directory-Benutzerkonten dediziert sind. Die Ressourcengesamtstruktur ist extern und wird von einem Hosting-Drittanbieter verwaltet. Die Ressourcengesamtstruktur enthält nur die Lync Server-Bereitstellung und eine synchronisierte Replikation der Benutzerkonten aus den lokalen Benutzerkonto-Gesamtstrukturen. Sie enthält keine anmeldefähigen Benutzerkonten. Exchange wird entweder in lokalen Benutzerkonto-Gesamtstrukturen zusammen mit Exchange Online (Hybrid) bereitgestellt oder E-Mail-Dienste für die lokalen Benutzerkonten werden ausschließlich von Exchange Online bereitgestellt.

Die Ressourcengesamtstruktur dient als gemeinsame Dienstumgebung für die lokalen Active Directory-Gesamtstrukturent, in denen sich die Benutzerobjekte befinden. Die Benutzerkonto-Gesamtstrukturen verfügen über eine unidirektionale Vertrauensbeziehung auf Gesamtstrukturebene zur Ressourcengesamtstruktur. Wenn Sie Lync Server in dieser Topologie bereitstellen, erstellen Sie in der Ressourcengesamtstruktur ein deaktiviertes Benutzerobjekt für jedes Benutzerkonto in den Benutzergesamtstrukturen. Ein Produkt zur Verzeichnissynchronisierung, wie MIIS, Microsoft Forefront Identity Manager (FIM) 2010 oder Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), verwaltet den Lebenszyklus der Benutzerkonten. Wenn ein neues Benutzerkonto in einer der Benutzergesamtstrukturen erstellt oder ein Benutzerkonto aus einer Gesamtstruktur gelöscht wird, synchronisiert das Verzeichnissynchronisierungs-Produkt die Entsprechung des Benutzers in der Ressourcengesamtstruktur. Weitere Informationen zur Konfiguration einer Bereitstellung mit mehreren Gesamtstrukturen finden Sie unter [Bereitstellen von Lync in einer Architektur mit mehreren Gesamtstrukturen (gemeinsames Hosting von Lync und Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).

