---
title: 'Lync Server 2013: Erstellen eines Geräts zum Testen der Update Funktionalität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad2fa5283561e1096cfe7e3053db59c3cd2e40e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Erstellen eines Geräts zum Testen der Update Funktionalität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können der Seite **Testgerät** ein Gerät hinzufügen und mit diesem Gerät anschließend die Funktionalität neuer Updates überprüfen, bevor die Updates auf Produktionsgeräten bereitgestellt werden. Sie können ein Gerät auf globaler Ebene (in der gesamten lync Server-Umgebung) oder auf einer einzigen Website testen. Sie identifizieren ein Testgerät über seine MAC-Adresse (Media Access Control) oder Seriennummer. Wenn Sie ein Gerät hinzufügen, wird es in der Liste auf **** der Seite Testgerät der lync Server-Systemsteuerung angezeigt.

<div>

## <a name="to-add-a-test-device"></a>So fügen Sie ein Testgerät hinzu

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **Gerät testen**.

3.  Klicken Sie auf **neu**, und klicken Sie dann entweder auf **globales Test Gerät** oder auf **Website Test Gerät**.

4.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie auf **globales Test Gerät**geklickt haben, fahren Sie mit dem nächsten Schritt fort.
    
      - Wenn Sie auf **Website Test Gerät**geklickt haben, wählen Sie in der Liste der verfügbaren Websites eine Website aus, und klicken Sie dann auf **OK**.

5.  Geben Sie in **Neues Testgerät**einen Namen für das Gerät in **Device Name**ein.

6.  Klicken **** Sie unter Bezeichnertyp entweder auf **MAC-Adresse** oder auf **Seriennummer**.

7.  Geben Sie im Feld **eindeutige Kennung** die Mac-Adresse oder die Seriennummer des Geräts ein.

8.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Erstellen von Test Geräten mithilfe von Windows PowerShell-Cmdlets

Test Geräte können mithilfe von Windows PowerShell und dem Cmdlet New-CsTestDevice erstellt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

Beim Erstellen von Testgeräten mit diesem Cmdlet müssen Sie zwei Schritte ausführen:

  - Geben Sie entweder MACAddress oder Seriennummer als IdentifierType an.

  - Schließen Sie den Bereich ein, wenn Sie die Geräte Identität angeben. Verwenden Sie zum Erstellen eines neuen Geräts im globalen Bereich eine Syntax ähnlich der folgenden:
    
        -Identity "global/WindowsPhone"
    
    Verwenden Sie zum Erstellen eines Testgeräts im Website Bereich die Syntax wie folgt:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>So erstellen Sie ein Testgerät mithilfe der Mac-Adresse

  - Mit diesem Befehl wird ein Testgerät im globalen Bereich erstellt und die Mac-Adresse als IdentifierType verwendet:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>So erstellen Sie ein Testgerät mithilfe der Seriennummer

  - Dieser Befehl erstellt ein neues Testgerät im Website Bereich (für die Website "Redmond") und verwendet die fortlaufende Zahl als IdentifierType:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

