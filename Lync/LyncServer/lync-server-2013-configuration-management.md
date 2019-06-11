---
title: 'Lync Server 2013: Konfigurationsverwaltung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa4bacdea1090351e9937e039fec184a1f59ab0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-management-in-lync-server-2013"></a>Konfigurationsverwaltung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-05-15_

Konfigurationsverwaltung ist der Vorgang zum Aufzeichnen und Nachverfolgen von Hardware-und Softwareressourcen sowie Systemkonfigurationsinformationen. Sie wird im Allgemeinen verwendet, um Softwarelizenzen zu überwachen, einen standardmäßigen Hardware-und Software-Build für Clientcomputer und Server zu verwalten und Namensstandards für neue Computer zu definieren. Die Konfigurationsverwaltung umfasst in der Regel die folgenden Kategorien:

  - **Hardware**   diese Kategorie verfolgt die Equipments, die die IT-Organisation besitzt, in der sich die Geräte befinden und die Geräte verwenden. Diese Informationen ermöglichen es einer Organisation, Upgrades zu planen und zu budgetieren, Standard-Hardware-Builds zu verwalten, den Wert von IT-Ressourcen zu Abrechnungszwecken zu melden und Diebstahl zu verhindern.

  - **Software**   diese Kategorie verfolgt Software, die auf jedem Computer installiert ist, die Versionsnummern und die Position, an der die Lizenzen aufbewahrt werden. Diese Informationen helfen bei der Planung von Upgrades, um sicherzustellen, dass Software lizenziert ist, und erkennen das vorhanden sein von nicht autorisierten (und nicht lizenzierten) Software.

  - **Standard**   -Builds mit dieser Kategorie wird der aktuelle Standard Build für die Clientcomputer und Server nachverfolgt, und ob die Clientcomputer und Server diesen Standard erfüllen. Die Definition und Erzwingung von Standard-Builds hilft dem Supportpersonal, da das Personal nur eine begrenzte Anzahl von Versionen jeder Software verwalten muss.

  - **Kumulative Updates und Hotfixes**   diese Kategorie verfolgt, welche Service Packs getestet und für die Verwendung genehmigt wurden und welche Computer auf dem neuesten Stand sind. Diese Informationen sind wichtig, um das Risiko zu verringern, dass Computer gefährdet sind, und um Benutzer zu erkennen, die nicht genehmigte Updates installiert haben.

  - **Systemkonfigurationsinformationen**   in dieser Kategorie werden die Funktion eines Systems, die Interaktion zwischen Systemelementen und die Prozesse verfolgt, die von einem reibungslos funktionierenden System abhängen. So kann beispielsweise ein Proxy Server eines Drittanbieters auf einem einzelnen Server konfiguriert sein. Die Abhängigkeit des Proxyservers von diesem Server sollte verstanden werden, und Notfallpläne sind möglicherweise erforderlich, wenn ein Fehler auftritt. Wenn der Proxy Server auch für die Kommunikation mit einem anderen Front-End-Server konfiguriert werden kann, ändern sich wahrscheinlich Abhängigkeiten und Notfallpläne.

<div>

## <a name="implementing-configuration-management"></a>Implementieren der Konfigurationsverwaltung

Nachdem Sie festgestellt haben, welche Elemente verwaltet werden müssen, implementieren Sie die Konfigurationsverwaltung, indem Sie Daten sammeln und Daten melden. Der einfachste Ansatz für kleine Organisationen besteht darin, Daten manuell (Anzahl und Modell von Clientcomputern, Betriebssystem, installierte Software) zu erfassen und in einem Office Word-oder Office Excel-Dokument zu speichern. Bei größeren, komplexeren und sich ständig ändernden Systemen muss die Ermittlung von Ressourcen und die Erfassung detaillierter Informationen automatisiert werden. Entscheiden Sie, welche Informationen für Ihre Organisation relevant sind, und speichern Sie Sie in einer Datenbank.

Die Konfigurationsverwaltungsdatenbank ist ein hilfreiches Tool für die Unterstützung von Mitarbeitern und Verwaltung in den folgenden Bereichen:

  - **Sicherheitsüberwachung**   die Datenbank ermöglicht es Ihnen, Server zu identifizieren, auf denen lync Server-und Clientcomputer Systeme ausgeführt werden, auf denen Hotfixes angewendet werden müssen oder die die Installation eines Service Packs oder der neuesten Antivirus-Updates verpasst haben.

  - **Software Installation**   , die Client Softwareversionen identifiziert und diese nachverfolgt, unterstützt Administratoren bei der Planung von Versionsupdates und neuen Installationen sowie bei der Lizenzierung von Dokumentation und Compliance.

  - **Konfigurationsinformationen**   Wenn Sie eine aktuelle Liste aller Einstellungen beibehalten, die von Ihrer Standardeinstellung geändert wurden, können Sie Probleme schnell und effektiver beheben.

  - **Planen von Upgrades**   wenn eine Kapazitätsüberprüfung zeigt, dass für Ihre lync-Datenbankserver zusätzlicher Speicherplatz erforderlich ist, ist es wichtig zu wissen, ob jeder Server über einen internen RAID-Controller verfügt. Wenn ja, sind Sie das gleiche Modell? Haben Sie die gleiche Anzahl von Festplatten installiert? Die Konfigurationsverwaltungsdatenbank gibt den Typ des Datenträgers an, der installiert werden kann, die Nummer und den Aktualisierungspfad in jedem Fall.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Für die Konfigurationsverwaltung verwendete Tools

Es gibt viele Tools zum ermitteln, überwachen und melden von Ressourcen. Einige dieser Tools werden in diesem Abschnitt erläutert.

  - **Automatisierte Skripts**   Sie können einfache Skripts schreiben, um Elemente wie das Betriebssystem, die Service Pack-Ebene zu melden und zu bestimmen, ob Software auf einem bestimmten Satz von Computern vorhanden ist. Sie können diese Skripts in die genauen Anforderungen einer Organisation schreiben. Die erforderliche Anzahl von Skripts und deren Komplexität können jedoch dazu führen, dass Skripts für die Erstellung und Verwaltung kostspielig sind.

  - **Automatisierte Tools**   je nach Größe Ihres Unternehmens und Ihren organisatorischen Anforderungen können Sie die Verwendung automatisierter Tools in Frage stellen. Tools wie System Center Configuration Manager enthalten standardberichtsvorlagen (wie die Service Pack-Ebene) und ermöglichen es Ihnen auch, angepasste Berichte zu erstellen, beispielsweise für eine benutzerdefinierte Anwendung. Der System Center-Konfigurations-Manager kann auch verwendet werden, um Hardware-und Softwarekonfigurationen zu melden.

</div>

<div>

## <a name="relationship-with-change-management"></a>Beziehung mit Änderungsverwaltung

Die Konfigurationsverwaltung steht in engem Zusammenhang mit der Änderungsverwaltung. Die Konfigurationsverwaltung identifiziert den Bedarf an Änderungen und identifiziert und zeichnet, dass eine Änderung aufgetreten ist. So kann beispielsweise die Konfigurationsverwaltungsdatenbank verwendet werden, um Server zu identifizieren, für die ein Hotfix erforderlich ist. Die Änderungsverwaltung definiert dann den Vorgang zum Anwenden des Hotfixes.

Wenn umgekehrt ein neues Kumulatives Update bereitgestellt wird, sollte der Change Management-Prozess diese Informationen an das Konfigurationsverwaltungssystem übermitteln. Die Konfigurationsverwaltungstools müssen wahrscheinlich so konfiguriert werden, dass Sie die neue Software identifizieren, sodass Sie ermitteln und nachvollziehen können, wo und wann die Software bereitgestellt wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

