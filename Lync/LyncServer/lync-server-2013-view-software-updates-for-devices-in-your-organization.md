---
title: 'Lync Server 2013: Anzeigen von Softwareupdates für Geräte in Ihrer Organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce1940f92860d5ccd2d66c53a0a4da16cebada24
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Anzeigen von Softwareupdates für Geräte in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Mit lync Server 2013 verwenden Sie den Geräte Update-Webdienst, um Softwareupdates für die Geräte Ihrer Organisation anzuzeigen und zu verwalten. Diese Updates stehen in CAB-Dateien auf der Microsoft-Support Website unter zur Verfügung [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091). Nachdem Sie die CAB-Datei heruntergeladen haben, führen Sie das Cmdlet **Import-CSDeviceUpdate** aus, um die geräteaktualisierungsregeln aus der CAB-Datei zu importieren. Ausführliche Informationen zum **Import-CSDeviceUpdate** -Cmdlet finden Sie unter [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in der lync Server-Verwaltungsshell Dokumentation.

<div>


> [!TIP]  
> Bevor Sie ein neues Update in Ihrer Organisation bereitstellen, sollten Sie seine ordnungsgemäße Funktion auf einem Testgerät überprüfen.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>So zeigen Sie Softwareupdates für UC-Geräte an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Laden Sie die CAB-Datei [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)von der Microsoft-Support Website unter an einen Speicherort auf einem lync Server 2013 Computer herunter (beispielsweise C\\:\\Updates ucupdates. cab).

3.  Importieren Sie die geräteaktualisierungsregeln aus der C\\:\\Updates-ucupdates. CAB-Datei, indem Sie eines der folgenden Cmdlets ausführen:
    
      - Wenn sich die CAB-Datei auf demselben Computer befindet wie der Dienst, der aktualisiert werden soll (service:Redmond-websvc-2), führen Sie das folgende Cmdlet aus:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Wenn sich die CAB-Datei auf einem anderen Computer befindet als der Dienst, der aktualisiert werden soll (service:Redmond-websvc-3), führen Sie das folgende Cmdlet aus:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Geräteaktualisierung**.

6.  Klicken Sie auf der Seite **Geräteaktualisierung** auf ein Update in der Liste, und führen Sie eine der folgenden Aktionen aus:
    
      - **Abbrechen eines ausstehenden Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Ausstehende Updates abbrechen**, um die Bereitstellung des ausgewählten Updates auf den Geräten in Ihrer Organisation zu verhindern.
    
      - **Genehmigen eines Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Genehmigen**, um die Bereitstellung des ausgewählten Updates auf den Geräten in Ihrer Organisation zuzulassen.
    
      - **Wiederherstellen eines Updates.** Klicken Sie auf das Menü **Aktion** und anschließend auf **Wiederherstellen**, um die Bereitstellung eines zuvor genehmigten Updates auf den Geräten in Ihrer Organisation zuzulassen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

