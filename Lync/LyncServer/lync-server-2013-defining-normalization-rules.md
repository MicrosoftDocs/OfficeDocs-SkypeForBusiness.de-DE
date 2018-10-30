---
title: 'Lync Server 2013: Definieren von Normalisierungsregeln'
TOCTitle: Definieren von Normalisierungsregeln
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399071(v=OCS.15)
ms:contentKeyID: 49295813
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren von Normalisierungsregeln in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Die Normalisierungsregeln von Lync Server 2013 nutzen reguläre Ausdrücke aus dem .NET Framework, um gewählte Telefonnummern in das E.164-Format umzuwandeln, d. h. die Normalisierungregeln übersetzen die vom Benutzer gewählte Telefonnummer in das intern von Lync Server genutzte Format. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Ausführliche Informationen zu Normalisierungsregeln finden Sie unter [Wählpläne und Normalisierungsregeln in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation.

Nähere Informationen über das Erstellen von regulären Ausdrücken finden Sie im Artikel ".NET Framework Regular Expressions" unter [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel definieren oder bearbeiten:

  - Geben Sie im Tool **Normalisierungsregel erstellen** Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern an, und lassen Sie anschließend die Lync Server-Systemsteuerung das entsprechende Vergleichsmuster und eine Übersetzungsregel generieren.

  - Schreiben Sie reguläre Ausdrücke manuell, um das Vergleichsmuster und die Übersetzungsregel zu definieren.

## In diesem Abschnitt

  - [Erstellen oder Ändern einer Normalisierungsregel mit dem Tool zum Erstellen einer Normalisierungsregel in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Manuelles Erstellen oder Ändern einer Normalisierungsregel in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

## Siehe auch

#### Aufgaben

[Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)

