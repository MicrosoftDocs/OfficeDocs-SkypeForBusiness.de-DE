---
title: Deaktivieren der Netzwerkmedienumgehung
TOCTitle: Deaktivieren der Netzwerkmedienumgehung
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49890845
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Deaktivieren der Netzwerkmedienumgehung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-15_

Medienumgehungseinstellungen gelten global in einer gesamten Microsoft Lync Server 2013-Bereitstellung. Die Medienumgehung ermöglicht bei Anrufen die Umgehung des Vermittlungsservers. Ausführliche Informationen zur Verwendung der Medienumgehung finden Sie unter [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) im Abschnitt zur Planung. Sie können die Medienumgehung in der Lync Server-Systemsteuerung deaktivieren. Ausführliche Informationen zum Aktivieren und Konfigurieren der Medienumgehung finden Sie unter [Aktivieren der Netzwerkmedienumgehung](lync-server-2013-enabling-network-media-bypass.md)

## So deaktivieren Sie die Medienumgehung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**. Es ist immer nur eine Konfiguration vorhanden, und diese trägt stets den Namen "Global".

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Deaktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

7.  Klicken Sie auf **Commit**, um Ihre Änderungen zu speichern.

## Siehe auch

#### Aufgaben

[Aktivieren der Netzwerkmedienumgehung](lync-server-2013-enabling-network-media-bypass.md)

