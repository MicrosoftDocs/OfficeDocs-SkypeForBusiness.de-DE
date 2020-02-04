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
ms.openlocfilehash: b6298f7aa6a500a71c0b3732dd2f3d180e7192d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a>Konfigurieren von Windows 8 für die Verwendung virtueller Smartcards mit lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-03_

Ein zu berücksichtigender Faktor bei der Bereitstellung der zweistufigen Authentifizierung und der Smartcardtechnologie sind die Kosten der Implementierung. Windows 8 bietet eine Reihe neuer Sicherheitsfunktionen, und eines der interessantesten neuen Features ist die Unterstützung virtueller Smartcards.

Bei Computern, die mit einem TPM-Chip (Trusted Platform Module) ausgerüstet sind, der die Spezifikationen von Version 1.2 erfüllt, können Organisationen nun die Vorteile einer Smartcardanmeldung nutzen, ohne in zusätzliche Hardware investieren zu müssen. Weitere Informationen finden Sie unter Verwenden virtueller Smartcards mit Windows 8 unter [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a>So konfigurieren Sie Windows 8 für virtuelle Smartcards

1.  Melden Sie sich mit den Anmeldeinformationen eines lync-fähigen Benutzers beim Windows 8-Computer an.

2.  Bewegen Sie den Cursor auf der Windows 8-Startseite in die untere rechte Ecke des Bildschirms.

3.  Wählen Sie die Option **Suchen** und suchen Sie dann nach der **Command Prompt**.

4.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und wählen Sie dann **Als Administrator ausführen** aus.

5.  Öffnen Sie die TPM-Verwaltungskonsole (Trusted Platform Module), indem Sie den folgenden Befehl ausführen:
    
        Tpm.msc

6.  Vergewissern Sie sich in der TPM-Verwaltungskonsole, dass die TPM-Spezifikationsversion mindestens 1.2 ist.
    
    <div>
    

    > [!NOTE]  
    > Wird ein Dialogfeld angezeigt, in dem gemeldet wird, dass kein kompatibles Trusted Platform Module (TPM) gefunden wurde, sollten Sie sich vergewissern, dass der Computer ein kompatibles TPM hat und dass dieses im System-BIOS aktiviert ist.

    
    </div>

7.  Schließen Sie die TPM-Verwaltungskonsole.

8.  Erstellen Sie über die Eingabeaufforderung eine neue virtuelle Smartcard, indem Sie folgenden Befehl ausführen:
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert bereitstellen möchten, verwenden Sie „/pin prompt“ anstelle von „/pin default“.

    
    </div>

9.  Öffnen Sie über die Eingabeaufforderung die Computerverwaltungskonsole, indem Sie den folgenden Befehl ausführen:
    
        CompMgmt.msc

10. Wählen Sie in der Computerverwaltungskonsole den Eintrag **Geräte-Manager** aus.

11. Erweitern Sie **Smartcard-Leser**.

12. Vergewissern Sie sich, dass der neue virtuelle Smartcardleser erfolgreich erstellt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

