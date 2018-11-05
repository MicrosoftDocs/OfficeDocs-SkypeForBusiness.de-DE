---
title: Planungsprozess für große Besprechungen
TOCTitle: Planungsprozess für große Besprechungen
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205334(v=OCS.15)
ms:contentKeyID: 49295637
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planungsprozess für große Besprechungen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Im Pool für große Besprechungen wird jeweils immer nur eine große Besprechung unterstützt. Deshalb wird empfohlen, einen Planungsprozess für große Besprechungen zu implementieren, um Konflikte bei großen Besprechungen zu vermeiden. Durch einen solchen Planungsprozess soll das Einrichten großer Besprechungen vereinfacht werden. Diese Funktionalität wird nicht direkt von Lync Server oder Lync Server-Clients bereitgestellt. Das Ticketsystem des Supportteams Ihrer Organisation stellt soweit vorhanden eine Möglichkeit dar, um einen solchen Prozess zu implementieren.

Für Organisatoren von großen Besprechungen beinhaltet das Planen einer großen Besprechung die folgenden Schritte:

1.  Der Besprechungsorganisator oder die delegierte Person bestimmt den Zeitpunkt, die Dauer und den Umfang einer anstehenden Besprechung sowie die Liste der Referenten. Falls der erwartete Besprechungsumfang 250 Benutzer überschreitet, oder um die optimale Funktionalität für eine Besprechung mit weniger als 250 Benutzern sicherzustellen, reicht der Organisator oder die delegierte Person einen Antrag für eine große Besprechung ein.

2.  Die Planungsmitarbeiter überprüfen, ob der angeforderte Termin verfügbar ist. Da jeweils immer nur eine einzige große Besprechung im Pool unterstützt wird, müssen die Planungsmitarbeiter anhand des Kalenders für große Besprechungen feststellen, ob für den angeforderten Termin bereits eine andere Besprechung geplant ist. Falls der angeforderte Termin verfügbar ist, wird die Besprechungsanfrage genehmigt.

3.  Wenn die Besprechungsanfrage genehmigt wurde, verwenden die Planungsmitarbeiter (mithilfe von Anmeldeinformationen für den dedizierten Pool) das Onlinebesprechungs-Add-In für Lync 2013 zusammen mit Outlook, um eine Besprechung für den Pool für große Besprechungen einzurichten. Die URL für die Teilnahme an der Besprechung wird dem Antragsteller im Rahmen des Genehmigungshinweises bereitgestellt.

4.  Der Besprechungsorganisator oder die delegierte Person plant mithilfe von Outlook die anstehende Besprechung und fügt die URL für die Teilnahme an der Besprechung der Besprechungseinladung hinzu. Der Besprechungsorganisator oder die delegierte Person legt dann die Benutzer fest, die eingeladen werden sollen, und versendet die Besprechungseinladung.
    
    Die folgende Abbildung veranschaulicht einen typischen Anfrage- und Genehmigungsworkflow für die Planung großer Besprechungen.
    
    ![Workflow für Konferenzplanung](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "Workflow für Konferenzplanung")

