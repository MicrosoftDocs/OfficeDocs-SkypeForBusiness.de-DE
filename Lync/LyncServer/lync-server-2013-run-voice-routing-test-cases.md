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
ms.openlocfilehash: 06c7119d8b011a805ffbc19c3b63f8832f302556
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511142"
---
# <a name="run-voice-routing-test-cases-in-lync-server-2013"></a>Ausführen von Testfällen für das VoIP-Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

Sie können alle Testfälle in ihrer Testfall-Suite für das VoIP-Routing ausführen, oder Sie können einen oder mehrere ausgewählte Test Cases ausführen.

<div>

## <a name="to-run-all-voice-routing-test-cases"></a>So führen Sie alle Test Fälle für das VoIP-Routing aus

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf **Aktion** , und klicken Sie dann auf **alle ausführen**.
    
    Der Status "Pass" oder "Fehler" jedes Testfalls wird in der Spalte " **Pass/Fehler** " angezeigt. Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Pass/Fail** angezeigt.

5.  Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Test Falls. Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:
    
    1.  **Test Ergebnis:** Der Gesamtstatus der Pass-oder Fehlerzustände der Test Fall Ausführung.
    
    2.  **Normalisierungsregel:** Die erste Normalisierungsregel in den Wähleinstellungen, die für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt (der Wert im Feld **zu testende Zahl** ).
    
    3.  **Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem die Normalisierungsregel übersetzt wurde.
    
    4.  **Erste PSTN-Verwendung:** Der erste PSTN-Verwendungsdaten Satz (Public Switched Telephone Network) in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt.
    
    5.  **Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, der mit der gewählten Nummer übereinstimmt.
        
        <div>
        

        > [!NOTE]  
        > Der <STRONG>erwartete PSTN-Verwendungsdaten Satz</STRONG> und die <STRONG>erwarteten Routen</STRONG> Felder sind in der Konfiguration für das VoIP-Routing Test Case optional. Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.

        
        </div>

</div>

<div>

## <a name="to-run-one-or-more-selected-voice-routing-test-cases"></a>So führen Sie ein oder mehrere ausgewählte VoIP-Routing Testfälle aus

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.

4.  Klicken Sie auf der Seite **VoIP-Routing testen** auf die Namen der Test Fälle, die Sie ausführen möchten.

5.  Klicken Sie im Menü **Aktion** auf **ausgewählt ausführen**.
    
    Der Status "Pass" oder "Fehler" jedes Testfalls wird in der Spalte " **Pass/Fehler** " angezeigt. Wenn ein Testfall noch nicht ausgeführt wurde, wird N/a in der Spalte **Pass/Fail** angezeigt.

6.  Optional Wenn Sie detaillierte Ergebnisse für jeden Testfall anzeigen möchten, doppelklicken Sie auf den Namen des Test Falls. Die Ergebnisse werden im schattierten Bereich auf der rechten Seite der Seite **Testfall bearbeiten** angezeigt:
    
    1.  **Test Ergebnis:** Der Gesamtstatus der Pass-oder Fehlerzustände der Test Fall Ausführung.
    
    2.  **Normalisierungsregel:** Die erste Normalisierungsregel in den Wähleinstellungen, die für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt (der Wert im Feld **zu testende Zahl** ).
    
    3.  **Normalisierte Zahl:** Der Wert der gewählten Nummer, nachdem die Normalisierungsregel übersetzt wurde.
    
    4.  **Erste PSTN-Verwendung:** Der erste PSTN-Verwendungsdaten Satz in der VoIP-Richtlinie, der für diesen Testfall ausgewählt wurde, der mit der gewählten Nummer übereinstimmt.
    
    5.  **Erste Route:** Die erste VoIP-Route im ersten PSTN-Verwendungsdaten Satz, der mit der gewählten Nummer übereinstimmt.
        
        <div>
        

        > [!NOTE]  
        > Der <STRONG>erwartete PSTN-Verwendungsdaten Satz</STRONG> und die <STRONG>erwarteten Routen</STRONG> Felder sind in der Konfiguration für das VoIP-Routing Test Case optional. Wenn der Testfall diese Werte nicht angibt, ist das entsprechende Feld in den Testergebnissen leer.

        
        </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Testen des VoIP-Routings in lync Server 2013](lync-server-2013-test-voice-routing.md)  
[Durchführen von Tests für das VoIP-Routing in lync Server 2013](lync-server-2013-running-voice-routing-tests.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

