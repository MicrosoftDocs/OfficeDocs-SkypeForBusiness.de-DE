---
title: 'Lync Server 2013: Übersicht über den Director'
TOCTitle: Übersicht über den Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398879(v=OCS.15)
ms:contentKeyID: 49295463
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über den Director in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Ein Director ist ein Server mit Lync Server 2013, der Benutzeranforderungen authentifiziert, jedoch keine Benutzerkonten verwaltet. In den folgenden beiden Szenarien können Sie optional einen Director bereitstellen:

  - Wenn Sie den Zugriff durch externe Benutzer über die Bereitstellung von Edgeservern aktivieren, sollten Sie auch einen Director bereitstellen. In diesem Szenario authentifiziert der Director die externen Benutzer und leitet den Datenverkehr an interne Server weiter. Wenn externe Benutzer über einen Director authentifiziert werden, wird die Datenlast auf den Servern im Front-End-Pool reduziert. Der Director trägt außerdem dazu bei, interne Front-End-Pools vor möglicherweise bösartigem Datenverkehr zu schützen, beispielsweise bei Denial-of-Service-Angriffen. Wenn das Netzwerk während eines solchen Angriffs mit ungültigem externen Datenverkehr überflutet wird, endet dieser Datenverkehr beim Director.

  - Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, können Sie durch Hinzufügen eines Directors zu diesem Standort die Verarbeitung von Authentifizierungsanforderungen optimieren und die Leistung verbessern. In diesem Szenario werden alle Anforderungen zuerst zum Director geleitet, der sie dann an den richtigen Front-End-Pool weiterleitet.

