---
title: Löschen von Netzwerksubnetzen
TOCTitle: Löschen von Netzwerksubnetzen
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49890921
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von Netzwerksubnetzen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Mithilfe des folgenden Verfahrens können Sie ein Subnetz löschen. In der Lync Server-Systemsteuerung können Sie ein Netzwerksubnetz erstellen, ändern oder löschen. Weitere Informationen zum Erstellen oder Ändern von Netzwerksubnetzen finden Sie unter [Erstellen oder Ändern von Netzwerksubnetzen](lync-server-2013-create-or-modify-network-subnets.md)

In den meisten Bereitstellungen von Microsoft Lync Server 2013 mit Anrufsteuerung ist eine große Anzahl von Subnetzen vorhanden. Daher empfiehlt es sich häufig, Subnetze über die Lync Server-Verwaltungsshell zu konfigurieren. Von dort aus können Sie **New-CsNetworkSubnet** zusammen mit dem Windows PowerShell-Cmdlet **Import-CSV** aufrufen. Wenn Sie diese beiden Cmdlets zusammen verwenden, können Sie die Subnetzeinstellungen aus einer durch Trennzeichen getrennten Datei (Comma-Separated Values, CSV) abrufen und mehrere Subnetze gleichzeitig erstellen. Beispiele für die Erstellung von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSubnet).

## So löschen Sie ein Netzwerksubnetz

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie löschen möchten.
    

    > [!NOTE]
    > Sie können mehrere Subnetze in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Subnetze aus. Wenn Sie alle Subnetze auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.



5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Netzwerksubnetzen](lync-server-2013-create-or-modify-network-subnets.md)

