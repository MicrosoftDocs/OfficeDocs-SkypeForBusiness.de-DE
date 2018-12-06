---
title: 'Lync Server 2013: Überprüfen der Normalisierungsregeln für das Parken von Anrufen'
TOCTitle: Überprüfen der Normalisierungsregeln für das Parken von Anrufen
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398981(v=OCS.15)
ms:contentKeyID: 49295638
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Normalisierungsregeln für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Orbits für das Parken von Anrufen dürfen nicht normalisiert werden. Überprüfen Sie Ihre Wählpläne, um sicherzustellen, dass Orbitnummern nicht normalisiert werden. Wenn Sie eine zusätzliche Normalisierungsregel erstellen müssen, um eine Normalisierung von Orbits zu verhindern, führen Sie das Verfahren unter [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) aus, um eine neue Normalisierungsregel zu definieren. Legen Sie hierbei **Zu suchendes Muster** zur Identifizierung des Orbitbereichs und **Übersetzungsmuster** auf **$1** fest. Wenn Sie beispielsweise einen Orbit für das Parken von Anrufen von 7000 - 7999 zum Parken von Anrufen verwenden, müssen Sie **Zu suchendes Muster** als **^(7\\d{3})$** definieren und **Übersetzungsmuster** auf **$1** festlegen.


> [!IMPORTANT]
> Stellen Sie sicher, dass die standardmäßige Normalisierungsregel in Ihren Wählplänen nicht den Ausdruck <STRONG>^(\d*)</STRONG> enthält. Andernfalls wird die Normalisierungsregel für das Parken von Anrufen nicht ausgeführt.



## Siehe auch

#### Aufgaben

[Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md)

