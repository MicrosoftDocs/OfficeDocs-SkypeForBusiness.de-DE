---
title: 'Lync Server 2013: Problembehandlung beim lync VDI-Plug-in'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7afaa0067e4ca06f8bb40ff201b090a45c66f442
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Problembehandlung beim lync VDI-Plug-in in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Behandeln von Problemen bei der Installation des lync VDI-Plug-Ins auf einem Thin Client

Wenn Probleme beim Installieren des VDI-Plug-Ins auf einem Thin Client auftreten, überprüfen Sie Folgendes:

  - Stellen Sie sicher, dass in dem Ordner, den Sie in den Systemvariablen „TEMP“ und „TMP“ angegeben haben, ausreichend Speicherplatz vorhanden ist.

  - Stellen Sie sicher, dass der Schreibschutz deaktiviert ist. Entsprechende Anweisungen finden Sie in der Dokumentation des Geräteherstellers.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Problembehandlung für die Kopplung

Wenn die VDI-Plug-in-Kopplung fehlschlägt, wird das Kopplungs Symbol in der unteren rechten Ecke als rotes "X" angezeigt:

![Lync-VDI-Symbol mit erfolgreicher Kopplung] (images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync-VDI-Symbol mit erfolgreicher Kopplung")

Im folgenden sind mögliche Ursachen für Fehler und die erforderlichen Korrekturmaßnahmen zu finden.

  - **Die Benutzer haben bei der Anmeldung falsche Anmeldeinformationen eingegeben.**
    
    Der Benutzer sollte sich bei lync abmelden und sich erneut mit den korrekten Anmeldeinformationen anmelden. Das Kopplungsdialogfeld wird erneut angezeigt und gibt an, ob die Kopplung erfolgreich war.

  - **Eine andere Instanz des Remotedesktopclients wird bereits ausgeführt.**
    
    Wenn Sie in Windows die Remote Desktop Verbindung verwenden, sollten die Benutzer die folgenden Schritte ausführen:
    
    1.  Starten Sie den Task-Manager: Drücken Sie **ALT+STRG+ENTF**, und klicken Sie dann auf **Task-Manager starten**.
    
    2.  Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.
    
    3.  Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**. 
    
    4.  Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen. 

  - **Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**
    
    Nachdem das Plug-in auf dem lokalen Computer installiert wurde, sollten die folgenden Dateien unter C:\\Programmdateien\\Microsoft Office\\Ordner office15 (oder der entsprechende Laufwerkbuchstabe) vorhanden sein:
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    Wenn Probleme mit der VDI-Kopplung auftreten, stellen Sie sicher, dass diese Dateien auf dem lokalen Computer vorhanden sind.

  - **Der lync-Client wird auf dem lokalen Computer ausgeführt.**
    
    Wenn Sie das lync-VDI-Plug-in verwenden möchten, muss ein lync-Client nicht auf dem lokalen Computer ausgeführt werden, da andernfalls die Kopplung fehlschlägt. Als bewährte Methode sollte der Benutzer keinen lync-Client auf dem lokalen Computer installieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

