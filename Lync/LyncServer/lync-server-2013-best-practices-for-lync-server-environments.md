---
title: 'Lync Server 2013: bewährte Methoden für lync Server Umgebungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for Lync Server environments
ms:assetid: b0e45d84-09c8-4d3e-aad0-bc6f34ce233b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720348(v=OCS.15)
ms:contentKeyID: 63969642
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f65e7d210c069a5b629e0fbf093e3abea291ce6a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513022"
---
# <a name="best-practices-for-lync-server-2013-environments"></a>Bewährte Methoden für lync Server 2013 Umgebungen

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-04_

Die folgenden allgemeinen Prinzipien sollten auf den laufenden Betrieb Ihres Systems angewendet werden:

  - **Verstehen und Verwenden von MOF**     MOF ist eine Sammlung von bewährten Methoden, Grundsätzen und Modellen, die Unternehmen technische Anleitungen zur Verwaltung von IT-Ressourcen bereitstellen, beispielsweise tägliche lync Server 2013 Vorgänge. Die folgenden MOF-Richtlinien können Ihnen dabei helfen, die Zuverlässigkeit, Verfügbarkeit, Unterstützung und Verwaltbarkeit von unternehmenskritischen Produktionssystemen für Microsoft-Produkte zu erreichen. Weitere Informationen finden Sie unter [Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939).

  - Informationen **zu bewährten Methoden für lync Server 2013**     Es wird empfohlen, praktische und bewährte Verfahren zum Verwalten von lync Server 2013 zu implementieren. Die Verwendung bewährter, getesteter und dokumentierter Methoden zur Verwaltung von Vorgängen ist möglicherweise effizienter als die Entwicklung eigener Methoden.

  - **Separate Vorgänge in tägliche, wöchentliche und monatliche Prozesse**     Dokumentieren Sie die erforderlichen Betriebsaufgaben, die Sie regelmäßig ausführen. Durch Dokumentieren der Vorgehensweise können Sie sicherstellen, dass Ihre Informationen beibehalten werden, wenn sich Ihre Betriebsumgebung ändert, beispielsweise wenn neue Technologien bereitgestellt werden oder Änderungen am Personal vorgenommen werden. Es wird empfohlen, dass Betriebsaufgaben in verwaltbare Arbeitslasten aufgeteilt werden, bei denen Aufgaben täglich, wöchentlich und monatlich ausgeführt werden. Tägliche Aufgaben konzentrieren sich auf die Funktionsweise eines Systems, und monatliche Aufgaben würden sich stärker auf die Sicherstellung der langfristigen Integrität eines Systems konzentrieren.
    
    Dieses Dokument kann in Umgebungen verwendet werden, in denen nur Instant Messaging/Presence-Komponenten (im/p) oder Chat/p mit Enterprise-VoIP bereitgestellt werden. Wenn Aufgaben oder Prüflistenelemente für Enterprise-VoIP spezifisch sind, wird dies erwähnt, und wenn Ihre Umgebung nicht Enterprise-VoIP enthält, wird der Teil möglicherweise übersprungen.

  - **Bereitstellen der für den Betriebs lync Server 2013**     erforderlichen Tools Es stehen zahlreiche Tools zur Verfügung, mit denen Sie Probleme beheben, Aufgaben automatisieren und die lync Server 2013 Umgebung überwachen und warten können. Definieren Sie einen Standardsatz von Tools für Ihre Organisation, damit die Aufgaben, die von dem Betriebsteam ausgeführt werden, genau, effizient, konsistent und kontrolliert ausgeführt werden. Sie sollten auch Verfahren zum Verfolgen von Vorfällen und größeren Konfigurationsänderungen implementieren.

<div>

## <a name="reference"></a>Referenz

Im Hinblick auf Leser, die nicht bereits mit den Grundlagen der Serververwaltung im allgemeinen vertraut sind, bieten wir eine Übersicht über die Server Verwaltungsverfahren. Leser, die bereits mit der Serververwaltung vertraut sind, können diesen Abschnitt überspringen.

Bewährte Methoden sind Empfehlungen, die auf dem Wissen und der Erfahrung basieren, die IT-Spezialisten in vielen Umgebungen gesammelt haben. Sie bieten Standardverfahren für typische Aufgaben, die ihre lync Server Administratoren täglich ausführen müssen, und Listen die Tools auf, die Sie zum Verwalten einer lync Server Umgebung verwenden sollten.

Zu den typischen Aufgaben für lync-Administratoren gehören folgende:

  - **Kapazitäts-und Verfügbarkeitsverwaltung**     Definieren Sie, wie und was gemessen werden soll, um zukünftige Kapazitätsanforderungen vorherzusagen, und Berichten Sie über die Kapazität, Zuverlässigkeit und Verfügbarkeit Ihrer Systeme. Sie müssen sicherstellen, dass die Größe der Server, auf denen lync Server ausgeführt werden, für die Verarbeitung der Systemlast ausgelegt ist und dass ungeplante Ausfallzeiten unter den in der Vereinbarung zum Service Level (SLA) definierten Ebenen aufbewahrt werden. Darüber hinaus müssen Sie ein Upgrade der Hardware durchführen, um die definierten Anforderungen weiterhin zu erfüllen.

  - **Change Management und Konfigurationsverwaltung**     Steuern, wie Änderungen an IT-Systemen vorgenommen werden. Dies sollte Tests, Anwendungs Feedback und Notfallpläne, Dokumentation aller Änderungen und Genehmigung von der Verwaltung umfassen, falls Probleme auftreten. Speichern Sie Ihre Software-und Hardwareressourcen sowie deren Konfigurationen.

  - **System Administration**     Skizzieren Sie Standardmethoden für administrative Aufgaben wie Datenbankverwaltung und Websiteverwaltung.

  - **Sicherheitsverwaltung**     Verfügen über eine detaillierte Richtlinie und einen Plan, der die Vertraulichkeit von Daten, die Datenintegrität und die Datenverfügbarkeit der IT-Infrastruktur schützt. Dies umfasst alltägliche Aktivitäten und Aufgaben im Zusammenhang mit der Verwaltung und Anpassung der IT-Sicherheitsinfrastruktur.

  - **System Problembehandlung**     Gliederungs Methoden für den Umgang mit unerwarteten Problemen, einschließlich der Schritte zum verhindern ähnlicher Probleme in der Zukunft.

  - Vereinbarungen zum Service **Level**     Verwalten Sie eine Reihe von Zielen für die Leistung der IT-Systeme, und Messen Sie die Leistung regelmäßig anhand dieser Ziele.

  - **Dokumentation**     Dokumentieren Sie Standardverfahren wie Konfigurationsinformationen und Lessons Learned, und stellen Sie Sie den Mitarbeitern zur Verfügung, die Sie benötigen. Wenn Änderungen an der Konfiguration vorgenommen werden, aktualisieren Sie die Dokumentation entsprechend.

</div>

<div>

## <a name="related-sections"></a>Verwandte Abschnitte

Lesen Sie die folgenden Themen zu Systemvorgängen, bevor Sie fortfahren:

  - [Kapazitäts-und Verfügbarkeitsverwaltung in lync Server 2013](lync-server-2013-capacity-and-availability-management.md)

  - [Änderungsverwaltung in lync Server 2013](lync-server-2013-change-management.md)

  - [Konfigurationsverwaltung in lync Server 2013](lync-server-2013-configuration-management.md)

  - [System Verwaltung in lync Server 2013](lync-server-2013-system-administration.md)

  - [Vereinbarungen zum Service Level in lync Server 2013](lync-server-2013-service-level-agreements.md)

  - [Dokumentation in lync Server 2013](lync-server-2013-documentation.md)

  - [Standard Verfahren in lync Server 2013](lync-server-2013-standard-procedures.md)

  - [Notfallverfahren in lync Server 2013](lync-server-2013-emergency-procedures.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Microsoft Operations Framework 4,0](https://go.microsoft.com/fwlink/p/?linkid=40939)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

