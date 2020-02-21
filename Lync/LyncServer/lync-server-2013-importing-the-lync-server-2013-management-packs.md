---
title: 'Lync Server 2013: Importieren der lync Server 2013 Management Packs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd5f09d80aa86c9c0f692fbe0e744a445067e74
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a>Importieren der lync Server 2013 Management Packs

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie Management Packs installieren – Software, die festlegt, welche Elemente System Center Operations Manager überwachen kann und wie diese Elemente überwacht werden sollen und wie Warnungen ausgelöst werden sollen und gemeldet. Lync Server 2013 enthält zwei System Center Operations Manager-Management Packs, die die folgenden Funktionen bieten:

  - Das Component and User Management Pack (Microsoft.ls.2013.Monitoring.ComponentAndUser.MP) verfolgt lync Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den Kommunikationsdatensätzen (KDS) oder der Quality of Experience (QoE) protokolliert wurden. Datenbanken. Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per e-Mail, Chatnachrichten oder SMS-Messaging benachrichtigt werden. Mit der SMS-Technologie werden Textnachrichten von einem mobilen Gerät zu einem anderen gesendet.)
    
    <div>
    

    > [!NOTE]  
    > Ausführliche Informationen zum Konfigurieren von Operations Manager-Benachrichtigungen finden Sie unter Konfigurieren der Benachrichtigung in der <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>TechNet-Bibliothek unter.

    
    </div>

  - Das Active Monitoring Management Pack (Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP) testet die Schlüssel lync Server Komponenten, beispielsweise das Anmelden beim System, das Austauschen von Chatnachrichten oder das tätigen von Anrufen an ein Telefon, das sich im öffentlichen Switch befindet, proaktiv. Telefonnetz (PSTN). Diese Tests werden mithilfe der Cmdlets für synthetische Transaktionen lync Server ausgeführt. Beispielsweise können Sie das Cmdlet **Test-CsIM** verwenden, um eine Konversation mit Sofortnachrichten zwischen einem Testbenutzerpaar zu simulieren. Wenn bei dieser simulierten Konversation mit Sofortnachrichten ein Fehler auftritt, wird eine Warnung generiert.

Sie müssen die Management Packs importieren. Wenn Sie die Management Packs nicht importieren, können Sie Operations Manager nicht verwenden, um lync Server Ereignisse zu überwachen oder lync Server synthetische Transaktionen auszuführen.

Das Komponenten-und das User Management Pack wird nur zum Überwachen von lync Server 2013 verwendet. Wenn Sie sich in einem Szenario mit Koexistenz befinden, in dem Sie sowohl lync Server 2013 als auch lync Server 2010 installiert haben, sollten Sie weiterhin die lync Server 2010 Management Packs für Ihre lync Server 2010 Computer verwenden.

<div>


> [!NOTE]  
> Zu den Management Packs für lync Server 2010 gehören das lync Server 2010 Monitoring Management Pack und das lync Server 2010-Gruppenchat Monitoring Management Pack.



</div>

Zum Importieren der Management Packs können folgende Tools verwendet werden:

  - **System Center Operations Manager**   mit dieser Methode verwenden Sie den Operations Manager, um die Überwachung für lync Server hinzuzufügen.

  - **Operations Manager-Shell**   Sie können die Operations Manager-Shell verwenden, um direkt zu importieren oder Probleme zu beheben, die beim Importieren von Management Packs mithilfe der System Center Operations Manager-Konsole auftreten.

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importieren der Management Packs mithilfe von System Center Operations Manager

1.  Laden Sie die Dateien "Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp" und "Microsoft.LS.2013.Monitoring.ComponentAndUser.mp" herunter.

2.  Klicken Sie in System Center Operations Manager auf **Verwaltung**.

3.  Klicken Sie auf der **** Verwaltungsseite mit der rechten Maustaste auf **Management Packs**, und klicken Sie anschließend auf **Management Packs importieren**.

4.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.

5.  Klicken Sie im Dialogfeld **Online Katalogverbindung** auf **Abbrechen** , um zu verhindern, dass Operations Manager Online geht, um zu überprüfen, ob für die lync Server Management Packs Abhängigkeiten vorhanden sind. Wenn Sie System Center Operations Manager 2012 verwenden, klicken Sie auf **Nein**.

6.  Suchen Sie im Dialogfeld **Zu importierende Management Packs auswählen** die Dateien **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** und **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp**, und wählen Sie sie aus, und klicken Sie anschließend auf **Öffnen**. Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie dann die STRG-TASTE gedrückt, und klicken Sie dann auf die zweite Datei.

7.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**. Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist. Wenn dies der Fall ist, kopieren Sie die Dateien in einen anderen Ordner, und starten Sie den Import- und Installationsvorgang erneut.

8.  Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**. Beachten Sie, dass der Import- und Installationsvorgang mehrere Minuten dauern kann.

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a>Importieren von Management Packs mithilfe der Operations Manager-Shell

Im Allgemeinen ist es einfacher, die Management Packs mithilfe von Operations Manager zu importieren. Wenn jedoch ein Fehler auftritt und der Import fehlschlägt, stellt die Konsole nicht immer angemessene Fehlerberichte bereit. Im Vergleich dazu enthält die Operations Manager-Shell detaillierte Informationen. Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Probleme auftreten, importieren Sie das Paket mithilfe der Operations Manager-Shell. Die Operations Manager-Shell enthält weitere Informationen, die Ihnen helfen können zu ermitteln, warum der Import fehlgeschlagen ist.

Wenn Sie System Center Operations Manager 2007 R2 verwenden, führen Sie das folgende Verfahren aus:

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **System Center Operations Manager 2007 R2**, und klicken Sie dann auf **Operations Manager-Shell**.

2.  Geben Sie in der Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung ein, wobei Sie den tatsächlichen Pfad zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP verwenden, und drücken Sie dann die EINGABETASTE:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  Wiederholen Sie nach dem Importieren des ersten Management Packs den Prozess, indem Sie den Pfad zur Kopie der Datei "Microsoft.LS.2013.Monitoring.ComponentAndUser.mp" verwenden:
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  Schließen Sie die Operations Manager-Shell.

Wenn Sie System Center Operations Manager 2012 verwenden, führen Sie dieses Verfahren stattdessen aus:

1.  Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft System Center 2012**, dann auf **Operations Manager**, und klicken Sie dann auf **Operations Manager-Shell**.

2.  Geben Sie in der Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung ein, wobei Sie den tatsächlichen Pfad zu Ihrer Kopie der Datei Microsoft.ls.2013.Monitoring.ActiveMonitoring.MP verwenden, und drücken Sie dann die EINGABETASTE:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  Wiederholen Sie nach dem Importieren des ersten Management Packs den Prozess, indem Sie den Pfad zur Kopie der Datei "Microsoft.LS.2013.Monitoring.ComponentAndUser.mp" verwenden:
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

