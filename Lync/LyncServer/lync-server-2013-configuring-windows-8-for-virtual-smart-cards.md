---
title: 'Lync Server 2013: Konfigurieren von Windows 8 für virtuelle Smartcards'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb8fe9fb9bcca80e7e84f19bdc484dc693b1ee68
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Konfigurieren Windows 8 für die Verwendung virtueller Smartcards mit lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-03_

Ein Faktor, der bei der Bereitstellung der zweistufigen Authentifizierung und der Smartcard-Technologie berücksichtigt werden muss, sind die Kosten der Implementierung. Windows 8 bietet eine Reihe von neuen Sicherheitsfunktionen, und eines der interessantesten neuen Features ist die Unterstützung virtueller Smartcards.

Für Computer, die mit einem TPM-Chip (Trusted Platform Module) ausgestattet sind, der die Spezifikationsversion 1,2 erfüllt, können Organisationen jetzt die Vorteile der Smartcard-Anmeldung nutzen, ohne dass zusätzliche Investitionen in Hardware getätigt werden. Weitere Informationen finden Sie unter Verwenden virtueller Smartcards mit Windows 8 unter [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>So konfigurieren Sie Windows 8 für virtuelle Smartcards

1.  Melden Sie sich mit den Anmeldeinformationen eines lync-aktivierten Benutzers am Windows 8 Computer an.

2.  Bewegen Sie den Cursor auf der Windows 8 Start Seite in die untere rechte Ecke des Bildschirms.

3.  Wählen Sie die **Such** Option aus, und suchen Sie dann nach **Eingabeaufforderung**.

4.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie dann **als Administrator ausführen**aus.

5.  Öffnen Sie die TPM-Verwaltungskonsole (Trusted Platform Module), indem Sie den folgenden Befehl ausführen:
    
        Tpm.msc

6.  Überprüfen Sie in der TPM-Verwaltungskonsole, ob Ihre TPM-Spezifikationsversion mindestens 1,2
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie ein Dialogfeld erhalten, das besagt, dass ein kompatibles TPM (Trust Platform Module) nicht gefunden werden kann, stellen Sie sicher, dass der Computer über ein kompatibles TPM-Modul verfügt und im System-BIOS aktiviert ist.

    
    </div>

7.  Schließen der TPM-Verwaltungskonsole

8.  Erstellen Sie über die Eingabeaufforderung eine neue virtuelle Smartcard mit dem folgenden Befehl:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert angeben möchten, verwenden Sie stattdessen die/PIN-Eingabeaufforderung.

    
    </div>

9.  Öffnen Sie an der Eingabeaufforderung die Computer Verwaltungskonsole, indem Sie den folgenden Befehl ausführen:
    
        CompMgmt.msc

10. Wählen Sie in der Konsole Computer Verwaltung die Option **Geräteverwaltung**aus.

11. Erweitern Sie **Smart Card Readers**.

12. Stellen Sie sicher, dass der neue virtuelle Smartcard-Leser erfolgreich erstellt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

