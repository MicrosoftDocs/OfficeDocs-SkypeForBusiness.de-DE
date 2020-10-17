---
title: 'Lync Server 2013: Konfigurationsverwaltung'
description: 'Lync Server 2013: Konfigurationsverwaltung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration management
ms:assetid: 00ea1196-cb40-427f-99a4-5e8037cbf367
ms:mtpsurl: https://technet.microsoft.com/library/Dn720316(v=OCS.15)
ms:contentKeyID: 63969570
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5999708811cc4a34cf846a1ddd481ba38e07c62
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552151"
---
# <a name="configuration-management-in-lync-server-2013"></a>Konfigurationsverwaltung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-05-15_

Bei der Konfigurationsverwaltung handelt es sich um den Vorgang der Aufzeichnung und Nachverfolgung von Hardware-und Softwareobjekten sowie Systemkonfigurationsinformationen. Er wird in der Regel zum Nachverfolgen von Softwarelizenzen, zum Verwalten einer Standardhardware und-Software für Clientcomputer und-Server und zum Definieren von Benennungsstandards für neue Computer verwendet. Die Konfigurationsverwaltung umfasst im Allgemeinen die folgenden Kategorien:

  - **Hardware**     In dieser Kategorie werden die Geräte aufgeführt, die die IT-Organisation besitzt, wo sich Geräte befinden und wer Geräte verwendet. Mithilfe dieser Informationen kann eine Organisation Upgrades planen und budgetieren, Standardhardware-Builds erstellen, den Wert von IT-Ressourcen für Kontoführungs Zwecke melden und Diebstahl verhindern.

  - **Software**     In dieser Kategorie werden Software verfolgt, die auf jedem Computer installiert ist, die Versionsnummern und wo die Lizenzen aufbewahrt werden. Mithilfe dieser Informationen können Sie Upgrades planen, sicherstellen, dass Software lizenziert ist, und das vorhanden sein von nicht autorisierten (und nicht lizenzierten) Software erkennen.

  - **Standard-Builds**     In dieser Kategorie wird der aktuelle Standard Build für die Clientcomputer und Server nachverfolgt, und ob die Clientcomputer und Server diesen Standard erfüllen. Das definieren und Erzwingen von Standard Builds unterstützt die Mitarbeiter, da die Mitarbeiter nur eine beschränkte Anzahl von Versionen jeder Software aufbewahren müssen.

  - **Kumulative Updates und Hotfixes**     In dieser Kategorie wird nachverfolgt, welche Service Packs getestet und für die Verwendung genehmigt wurden und welche Computer auf dem neuesten Stand sind. Diese Informationen sind wichtig, um das Risiko zu verringern, dass Computer kompromittiert werden, und um Benutzer zu erkennen, die nicht genehmigte Updates installiert haben.

  - Informationen zur System **Konfiguration**     In dieser Kategorie werden die Funktionen eines Systems, die Interaktion zwischen Systemelementen und die Prozesse verfolgt, die von einem reibungslos ausgeführten System abhängen. Beispielsweise kann ein Drittanbieter-Proxy Server auf einem einzelnen Server konfiguriert werden. Die Abhängigkeit des Proxyservers auf diesem Server sollte verstanden werden, und Notfallpläne sind möglicherweise erforderlich, wenn ein Fehler aufgetreten ist. Wenn der Proxy Server so konfiguriert werden kann, dass er auch mit einem anderen Front-End-Server kommuniziert, ändern sich wahrscheinlich Abhängigkeiten und Notfallpläne.

<div>

## <a name="implementing-configuration-management"></a>Implementieren der Konfigurationsverwaltung

Nachdem Sie festgestellt haben, welche Elemente verwaltet werden müssen, implementieren Sie die Konfigurationsverwaltung durch das Sammeln von Daten und Berichtsdaten. Der einfachste Ansatz für kleine Organisationen besteht darin, Daten manuell zu erfassen (Anzahl und Modell von Clientcomputern, Betriebssystem, installierte Software) und in einem Office Word-oder Office Excel-Dokument zu speichern. Für größere, komplexere und sich ständig verändernde Systeme müssen die Ermittlung von Objekten und die Sammlung detaillierter Informationen automatisiert werden. Entscheiden Sie, welche Informationen für Ihre Organisation relevant sind, und zeichnen Sie Sie in einer Datenbank auf.

Die Konfigurationsverwaltungsdatenbank ist ein nützliches Tool für Supportmitarbeiter und-Verwaltung in den folgenden Bereichen:

  - **Sicherheitsüberprüfungen**     Mit der Datenbank können Sie Server identifizieren, auf denen lync Server-und Clientcomputer Systeme ausgeführt werden, auf denen Hotfixes angewendet werden müssen oder die die Installation eines Service Packs oder der neuesten Antiviren-Updates verpasst haben.

  - **Software Installation**     Das Identifizieren von Client Softwareversionen und deren Nachverfolgung unterstützt Administratoren beim Planen von Versionsupdates und neuen Installationen sowie bei der Lizenzierung von Dokumentationen und der Compliance.

  - **Konfigurationsinformationen**     Wenn Sie eine aktuelle Liste aller Einstellungen beibehalten, die von ihrem Standardwert geändert wurden, können Sie Probleme schnell und effektiver behandeln.

  - **Planen von Upgrades**     Wenn bei einer Kapazitätsüberprüfung zusätzlicher Speicherplatz auf Ihren lync-Datenbankservern erforderlich ist, müssen Sie unbedingt wissen, ob jeder Server über einen internen RAID-Controller verfügt. Wenn dies der Fall ist, handelt es sich dabei um das gleiche Modell? Haben Sie die gleiche Anzahl von Datenträgern installiert? Die Konfigurationsverwaltungsdatenbank gibt den Typ des Datenträgers an, der installiert werden kann, die Nummer und den Aktualisierungspfad in jedem Fall.

</div>

<div>

## <a name="tools-used-for-configuration-management"></a>Für die Konfigurationsverwaltung verwendete Tools

Es gibt zahlreiche Tools zum ermitteln, überwachen und melden von Objekten. Einige dieser Tools werden in diesem Abschnitt erläutert.

  - **Automatisierte Skripts**     Sie können einfache Skripts schreiben, um Elemente wie Betriebssystem, Service Pack-Ebene und Software auf einem bestimmten Satz von Computern zu melden. Sie können diese Skripts in die genauen Anforderungen einer Organisation schreiben. Die erforderliche Anzahl von Skripts und deren Komplexität können Skripts jedoch teuer erstellen und warten lassen.

  - **Automatisierte Tools**     Je nach Größe Ihres Unternehmens und Ihren organisatorischen Anforderungen sollten Sie die Verwendung von automatisierten Tools in Frage stellen. Tools wie Microsoft Endpoint Configuration Manager enthalten standardberichtsvorlagen (wie Service Pack-Ebene) und ermöglichen Ihnen auch das Erstellen von benutzerdefinierten Berichten, beispielsweise für eine benutzerdefinierte Anwendung. Der Microsoft Endpoint Configuration Manager kann auch zum Melden von Hardware-und Softwarekonfigurationen verwendet werden.

</div>

<div>

## <a name="relationship-with-change-management"></a>Beziehung zur Änderungsverwaltung

Die Konfigurationsverwaltung steht im engen Zusammenhang mit der Änderungsverwaltung. Die Konfigurationsverwaltung gibt an, dass Änderungen erforderlich sind, und identifiziert und zeichnet eine Änderung auf. Beispielsweise kann die Konfigurationsverwaltungsdatenbank verwendet werden, um Server zu identifizieren, die einen Hotfix erfordern. Change Management definiert dann den Prozess für die Anwendung des Hotfixes.

Wenn umgekehrt ein neues Kumulatives Update ausgeführt wird, sollte der Änderungsverwaltungsprozess diese Informationen dem Konfigurationsverwaltungssystem bereitstellen. Die Konfigurationsverwaltungstools müssen möglicherweise so konfiguriert werden, dass die neue Software so identifiziert wird, dass Sie erkennt und nachverfolgen kann, wo und wann die Software bereitgestellt wird.

</div>

</div>

<span> </span>

</div>

</div>

</div>

