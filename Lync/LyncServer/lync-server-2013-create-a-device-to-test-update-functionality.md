---
title: 'Lync Server 2013: Erstellen eines Geräts zum Testen der Update Funktionalität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67712f981d8061b8dd3c90de812092e01dc5d1b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Erstellen eines Geräts zum Testen der Update Funktionalität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Sie können ein Gerät zur Seite **Testgerät** hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät auf globaler Ebene (in der gesamten lync Server Umgebung) oder an einem einzelnen Standort testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf der Seite **Test Gerät** des lync Server-Systemsteuerung angezeigt.

<div>

## <a name="to-add-a-test-device"></a>So fügen Sie ein Testgerät hinzu

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Testgerät**.

3.  Klicken Sie auf **Neu** und anschließend entweder auf **Globales Testgerät** oder **Standorttestgerät**.

4.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie auf **Globales Testgerät** geklickt haben, fahren Sie mit dem nächsten Schritt fort.
    
      - Wenn Sie auf **Standorttestgerät** geklickt haben, wählen Sie einen Standort aus der Liste der verfügbaren Standorte aus, und klicken Sie dann auf **OK**.

5.  Geben Sie unter **Neues Testgerät** im Feld **Gerätename** einen Namen für das Gerät ein.

6.  Klicken Sie unterhalb von **ID-Typ** entweder auf **MAC-Adresse** oder **Seriennummer**.

7.  Geben Sie im Feld **Eindeutige ID** die MAC-Adresse oder die Seriennummer des Geräts ein.

8.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Erstellen von Test Geräten mithilfe von Windows PowerShell-Cmdlets

Test Geräte können mit Windows PowerShell und dem New-CsTestDevice-Cmdlet erstellt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

Beim Erstellen von Testgeräten mithilfe dieses Cmdlets müssen Sie die folgenden beiden Schritte ausführen:

  - Geben Sie MACAddress oder SerialNumber als IdentifierType an.

  - Fügen Sie beim Angeben der Geräteidentität die Ebene hinzu. Verwenden Sie zum Erstellen eines neuen Geräts auf globaler Ebene Syntax, die so oder ähnlich aussieht:
    
        -Identity "global/WindowsPhone"
    
    Verwenden Sie zum Erstellen eines neuen Geräts auf Standortebene Syntax, die so oder ähnlich aussieht:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>So erstellen Sie ein Test Gerät mithilfe der Mac-Adresse

  - Mit diesem Befehl wird ein Testgerät auf globaler Ebene und mit der MAC-Adresse als IdentifierType erstellt:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>So erstellen Sie mithilfe der Seriennummer ein Test Gerät

  - Mit diesem Befehl wird ein neues Testgerät auf Standortebene (für den Standort "Redmond") und mit der Seriennummer als IdentifierType erstellt:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Weitere Informationen finden Sie im Hilfethema zum [New-CsTestDevice-](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) Cmdlet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

