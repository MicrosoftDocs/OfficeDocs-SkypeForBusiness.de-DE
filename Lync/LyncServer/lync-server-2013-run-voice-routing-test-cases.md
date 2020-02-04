---
title: 'Lync Server 2013: Ausführen von Testfällen für das VoIP-Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run voice routing test cases
ms:assetid: fb4d32df-b9ea-4944-8cd7-a6102c78c465
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413068(v=OCS.15)
ms:contentKeyID: 48185948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14f2df8a04c5efbf8c62bc4e17bbdd156913daae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Ausführen von Testfällen für das VoIP-Routing in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Sie können alle Testfälle in Ihrer Suite für den sprach Routing Test ausführen, oder Sie können einen oder mehrere ausgewählte Test Cases ausführen.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>So führen Sie alle Test Cases für VoIP-Routing aus

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** , und klicken Sie dann auf VoIP- **Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **Aktion** und dann auf **alle ausführen**.
    
    Der Pass-oder Fehlerstatus jedes Testfalls wird in der Spalte **Pass/Fehler** angezeigt. Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Durchlauf/Fehler** angezeigt.

5.  Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Testfalls. Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:
    
    1.  **Test Ergebnis:** Gesamtdurchlauf-oder Fehlerstatus des Test Fall Laufs
    
    2.  **Normalisierungsregel:** Die erste Normalisierungsregel im Wählplan, die für diesen Testfall ausgewählt wurde, der der gewählten Nummer entspricht (dem Wert im Feld " **zu testende Zahl** ").
    
    3.  **Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem Sie von der Normalisierungsregel übersetzt wurde.
    
    4.  **Erste PSTN-Nutzung:** Der erste PSTN-Nutzungs Eintrag (Public Switched Telephone Network) in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der der gewählten Nummer entspricht.
    
    5.  **Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, die der gewählten Nummer entspricht.
        
        <div>
        

        > [!NOTE]  
        > Der <STRONG>erwartete PSTN-Nutzungsdaten Satz</STRONG> und die <STRONG>erwarteten Route</STRONG> -Felder sind in der Konfiguration des Testfalles für sprach Routing optional. Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>So führen Sie einen oder mehrere ausgewählte VoIP-Test Cases aus

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**, und klicken Sie dann auf VoIP- **Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf die Namen der Testfälle, die Sie ausführen möchten.

5.  Klicken Sie im Menü **Aktion** auf **ausgewählte ausführen**.
    
    Der Pass-oder Fehlerstatus jedes Testfalls wird in der Spalte **Pass/Fehler** angezeigt. Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Durchlauf/Fehler** angezeigt.

6.  Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Testfalls. Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:
    
    1.  **Test Ergebnis:** Gesamtdurchlauf-oder Fehlerstatus des Test Fall Laufs
    
    2.  **Normalisierungsregel:** Die erste Normalisierungsregel im Wählplan, die für diesen Testfall ausgewählt wurde, der der gewählten Nummer entspricht (dem Wert im Feld " **zu testende Zahl** ").
    
    3.  **Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem Sie von der Normalisierungsregel übersetzt wurde.
    
    4.  **Erste PSTN-Nutzung:** Der erste PSTN-Verwendungs Eintrag in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der der gewählten Nummer entspricht.
    
    5.  **Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, die der gewählten Nummer entspricht.
        
        <div>
        

        > [!NOTE]  
        > Der <STRONG>erwartete PSTN-Nutzungsdaten Satz</STRONG> und die <STRONG>erwarteten Route</STRONG> -Felder sind in der Konfiguration des Testfalles für sprach Routing optional. Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Testen des VoIP-Routings in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Ausführen von Tests für das VoIP-Routing in Lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

