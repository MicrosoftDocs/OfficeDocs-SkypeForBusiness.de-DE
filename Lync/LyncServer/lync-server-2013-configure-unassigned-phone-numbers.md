---
title: Konfigurieren von nicht zugewiesenen Telefonnummern
TOCTitle: Konfigurieren von nicht zugewiesenen Telefonnummern
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182559(v=OCS.15)
ms:contentKeyID: 49294929
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von nicht zugewiesenen Telefonnummern

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In Lync Server können Sie die Vorgehensweise für eingehende Anrufe an Telefonnummern konfigurieren, die zwar für Ihre Organisation gültig, jedoch keinem Benutzer oder Telefon zugewiesen sind. Zum Konfigurieren der Verarbeitung solcher Anrufe richten Sie eine Tabelle mit nicht zugewiesenen Nummern ein. Mithilfe der Tabelle können Sie die Anrufe an eine Ansageanwendung oder an einen Exchange UM-Server weiterleiten.

Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.


> [!IMPORTANT]
> Bevor Sie die Tabelle nicht zugewiesener Nummern konfigurieren, müssen Sie eine oder mehrere Ansagen definieren oder eine automatische Exchange UM-Telefonzentrale einrichten. Einzelheiten zum Erstellen von Ansagen finden Sie unter <A href="lync-server-2013-create-an-announcement.md">Erstellen einer Ansage in Lync Server 2013</A>. Wenn Sie überprüfen möchten, ob Sie die Exchange UM-Einstellungen konfiguriert haben, führen Sie das Cmdlet <STRONG>Get-CsExUmContact</STRONG> aus. Einzelheiten dazu finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.



## In diesem Abschnitt

  - [Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Löschen eines Bereichs nicht zugewiesener Nummern](lync-server-2013-delete-an-unassigned-number-range.md)

