---
title: 'Lync Server 2013: Problembehandlung beim lync VDI-Plug-in'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1d75e0801ec16957083f2e9fef043080c771ea9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a>Problembehandlung für das lync VDI-Plug-in in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-10_

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a>Beheben von Problemen beim Installieren des lync VDI-Plug-Ins auf einem Thin-Client

Wenn beim Installieren des VDI-Plug-Ins auf einem Thin-Client Probleme auftreten, überprüfen Sie Folgendes:

  - Stellen Sie sicher, dass im Ordner, den Sie in den Systemvariablen "TEMP" und "TMP" angegeben haben, ausreichend Speicherplatz vorhanden ist

  - Stellen Sie sicher, dass der Schreibschutz deaktiviert ist. Entsprechende Anweisungen finden Sie Dokumentation des Geräteherstellers.

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a>Behebung von Problemen bei der Paarung

Wenn die Paarung des VDI-Plug-Ins fehlschlägt, wird das Paarungssymbol unten rechts als rotes “X” angezeigt:

![Lync-VDI-Symbol mit erfolgreicher Kopplung](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync-VDI-Symbol mit erfolgreicher Kopplung")

Im Folgenden finden Sie mögliche Gründe für Fehler und Korrekturmaßnahmen.

  - **Der Benutzer hat bei der Anmeldung falsche Anmeldeinformationen eingegeben.**
    
    Der Benutzer sollte sich bei lync abmelden und sich mit den korrekten Anmeldeinformationen erneut anmelden. Das Paarungsdialogfeld wird erneut angezeigt und gibt an, ob die Paarung erfolgreich war.

  - **Eine andere Instanz des Remotedesktop-Clients wird bereits ausgeführt**
    
    Wenn die Remote Desktop Verbindung in Windows verwendet wird, sollten Benutzer folgende Schritte ausführen:
    
    1.  Starten Sie den Task-Manager: Drücken Sie **Alt+Strg+Entf**, und klicken Sie dann auf **Task-Manager starten**.
    
    2.  Klicken Sie auf die Registerkarte **Prozesse**, und suchen Sie in der Liste nach allen Prozessen mit dem Namen **mstsc.exe**.
    
    3.  Markieren Sie alle **mstsc.exe**-Prozesse, und klicken Sie dann auf **Prozess beenden**.
    
    4.  Starten Sie eine neue Remotedesktopsitzung, und versuchen Sie erneut, eine Verbindung herzustellen.

  - **Die erforderlichen Dateien wurden nicht ordnungsgemäß installiert.**
    
    Nachdem das Plug-in auf dem lokalen Computer installiert wurde, sollten die folgenden Dateien unter C:\\Program Files\\Microsoft Office\\Office15 (oder dem entsprechenden Laufwerksbuchstaben) vorhanden sein:
    
      - LyncVdiPlugin. dll
    
      - UcVdi. dll
    
    Wenn Probleme mit der VDI-Paarung auftreten, stellen Sie sicher, dass diese Dateien auf dem lokalen Computer vorhanden sind.

  - **Der lync-Client wird auf dem lokalen Computer gestartet.**
    
    Für die Verwendung des lync VDI-Plug-ins darf ein lync-Client nicht auf dem lokalen Computer ausgeführt werden, andernfalls tritt ein Verbindungsfehler auf. Als bewährte Methode sollte der Benutzer keinen lync-Client auf dem lokalen Computer installieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

