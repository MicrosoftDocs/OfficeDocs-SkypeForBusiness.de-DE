---
title: 'Lync Server 2013: Konfigurieren der Tabelle nicht zugewiesener Nummern'
TOCTitle: Konfigurieren der Tabelle nicht zugewiesener Nummern
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399053(v=OCS.15)
ms:contentKeyID: 49295788
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

In Lync Server 2013 können Sie angeben, was bei eingehenden Anrufen bei Telefonnummern geschieht, die innerhalb der Organisation gültig sind, jedoch keinem Benutzer oder Telefon zugewiesen sind. Sie können für Anrufer eine Ansage wiedergeben, sie an ein anderes Ziel weiterleiten oder beides.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr dann eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.


> [!IMPORTANT]
> Vor der Konfiguration der Tabelle nicht zugewiesener Rufnummern müssen entweder Ankündigungen für Ihr System definiert oder eine automatische Telefonzentrale in Exchange Unified Messaging (UM) eingerichtet werden.




> [!TIP]
> Wenn ein Anruf bei einer nicht zugewiesenen Nummer eingeht, durchsucht Lync Server die Tabelle nicht zugewiesener Rufnummern von oben nach unten und verwendet den ersten übereinstimmenden Bereich. Sie sollten also als letzte Lösungsmöglichkeit eine Aktion definieren, die für den letzten Bereich in der Tabelle ausgeführt werden soll.



## In diesem Abschnitt

[Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Erstellen einer Ansage in Lync Server 2013](lync-server-2013-create-an-announcement.md)

