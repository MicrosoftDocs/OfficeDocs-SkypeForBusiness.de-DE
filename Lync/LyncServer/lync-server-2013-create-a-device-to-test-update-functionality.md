---
title: Erstellen eines Geräts zum Testen der Updatefunktion
TOCTitle: Erstellen eines Geräts zum Testen der Updatefunktion
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182587(v=OCS.15)
ms:contentKeyID: 49295446
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen eines Geräts zum Testen der Updatefunktion

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können ein Gerät zur Seite **Testgerät** hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät global (innerhalb der gesamten Lync Server-Umgebung) oder innerhalb eines einzelnen Standorts testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **Testgerät** in der Lync Server-Systemsteuerung angezeigt.

## So fügen Sie ein Testgerät hinzu

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Testgerät**.

3.  Klicken Sie auf **Neu** und anschließend entweder auf **Globales Testgerät** oder **Standorttestgerät**.

4.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie auf **Globales Testgerät** geklickt haben, fahren Sie mit dem nächsten Schritt fort.
    
      - Wenn Sie auf **Standorttestgerät** geklickt haben, wählen Sie einen Standort aus der Liste der verfügbaren Standorte aus, und klicken Sie dann auf **OK**.

5.  Geben Sie unter **Neues Testgerät** im Feld **Gerätename** einen Namen für das Gerät ein.

6.  Klicken Sie unterhalb von **ID-Typ** entweder auf **MAC-Adresse** oder **Seriennummer**.

7.  Geben Sie im Feld **Eindeutige ID** die MAC-Adresse oder die Seriennummer des Geräts ein.

8.  Klicken Sie auf **Commit ausführen**.

## Erstellen von Testgeräten mithilfe von Windows PowerShell-Cmdlets

Testgeräte können auch mit der Windows PowerShell und dem New-CsTestDevice-Cmdlet erstellt werden. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

Beim Erstellen von Testgeräten mithilfe dieses Cmdlets müssen Sie die folgenden beiden Schritte ausführen:

  - Geben Sie MACAddress oder SerialNumber als IdentifierType an.

  - Fügen Sie beim Angeben der Geräteidentität die Ebene hinzu. Verwenden Sie zum Erstellen eines neuen Geräts auf globaler Ebene Syntax, die so oder ähnlich aussieht:
    
        -Identity "global/WindowsPhone"
    
    Verwenden Sie zum Erstellen eines neuen Geräts auf Standortebene Syntax, die so oder ähnlich aussieht:
    
        -Identity "site:Redmond/WindowsPhone"

## So erstellen Sie ein Testgerät mithilfe der MAC-Adresse

  - Mit diesem Befehl wird ein Testgerät auf globaler Ebene und mit der MAC-Adresse als IdentifierType erstellt:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

## So erstellen Sie ein Testgerät mithilfe der Seriennummer

  - Mit diesem Befehl wird ein neues Testgerät auf Standortebene (für den Standort "Redmond") und mit der Seriennummer als IdentifierType erstellt:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

Weitere Informationen finden Sie im Hilfethema für das [New-CsTestDevice](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTestDevice)-Cmdlet.

