---
title: 'Lync Server 2013: Zurücksetzen von migrierten Benutzern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: deda1ec30ef5267acd8b3826b77077e7902d98e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511262"
---
# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Wiederherstellen migrierter Benutzer in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-07_

Wenn Sie ein Rollback für die Funktion des einheitlichen Kontaktspeichers ausführen müssen, führen Sie die Kontakte nur zurück, wenn Sie den Benutzer zurück in Exchange 2010 oder lync Server 2010 bewegen. Wenn Sie ein Rollback ausführen möchten, deaktivieren Sie die Richtlinie für den Benutzer, und führen Sie dann das Cmdlet **Invoke-CsUcsRollback** aus. Das Ausführen von **Invoke-CsUcsRollback** alleine reicht nicht aus, um ein dauerhaftes Rollback sicherzustellen, da die Migration des einheitlichen Kontaktspeichers erneut initiiert wird, wenn die Richtlinie nicht deaktiviert ist. Wenn beispielsweise ein Rollback für einen Benutzer durchgeführt wird, da Exchange 2013 auf Exchange 2010 zurückgesetzt wird und das Postfach des Benutzers in Exchange 2013 verschoben wird, wird die Migration des einheitlichen Kontaktspeichers sieben Tage nach dem Rollback erneut initiiert, solange der einheitliche Kontaktspeicher für den Benutzer in der Benutzer Dienste-Richtlinie weiterhin aktiviert ist.

<div>


> [!IMPORTANT]  
> Das Cmdlet " <STRONG>CsUser</STRONG> " rollt den Kontaktspeicher des Benutzers in den folgenden Situationen automatisch von Exchange 2013 auf lync Server 2013 zurück: 
> <UL>
> <LI>
> <P>Wenn Benutzer von lync Server 2013 zu lync Server 2010 verschoben werden.</P>
> <LI>
> <P>Wenn Benutzer über lokale Migrationen migriert werden, beispielsweise wenn ein Benutzer von lync online zu lync Server 2013 lokal verschoben wird oder umgekehrt.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel: 
> <UL>
> <LI>
> <P>Wenn Sie Kontaktlisten exportieren, bevor die Benutzer Kontakte zu Exchange 2013 migriert werden, und dann nach der Migration dieselben Daten importieren, sind die Daten des einheitlichen Kontaktspeichers und die Kontaktlisten beschädigt.</P>
> <LI>
> <P>Wenn Sie Benutzerinformationen nach dem Migrieren von Benutzern zu Exchange 2013 exportieren, die Migration zurücksetzen und dann aus irgendeinem Grund die Daten nach der Migration importieren, werden die Daten und Kontaktlisten für den einheitlichen Kontaktspeicher beschädigt.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Bevor Sie ein Exchange-Postfach von Exchange 2013 in Exchange 2010 migrieren, muss der Exchange-Administrator sicherstellen, dass der lync Server Administrator zunächst die lync Server Benutzer Kontakte von Exchange 2013 auf lync Server zurückgesetzt hat. Informationen zum Zurücksetzen von Kontakten für den einheitlichen Kontaktspeicher auf lync Server finden Sie unter procedure to Rollback Unified Contact Store Contacts from Exchange 2013 to lync Server 2013 "weiter unten in diesem Abschnitt.



</div>

Im folgenden Verfahren wird beschrieben, wie Sie ein Rollback für Benutzerkontakte ausführen. Wenn Sie das **Move-CsUser-** Cmdlet verwenden, um Benutzer zwischen lync Server 2013 und lync Server 2010 zu verschieben, können Sie diese Schritte überspringen, da das Cmdlet **Move-CsUser** automatisch unifed Kontaktspeicher zurücksetzt, wenn Benutzer von lync Server 2013 in lync Server 2010 verschoben werden. Mit **Move-CsUser** wird die Richtlinie für den einheitlichen Kontaktspeicher nicht deaktiviert, sodass die Migration zu einem einheitlichen Kontaktspeicher wiederholt wird, wenn der Benutzer zurück in lync Server 2013 verschoben wird.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>So führen Sie ein Rollback für Benutzer Kontakte von lync Server 2013 auf lync Server 2010 aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Deaktivieren Sie den einheitlichen Kontaktspeicher für die Benutzer, für die ein Rollback ausgeführt werden soll, damit sie nach dem Rollback nicht erneut migriert werden. (Führen Sie diesen Schritt nur aus, wenn Sie sicherstellen möchten, dass die Benutzer in Zukunft nicht erneut migriert werden.) Geben Sie an der Befehlszeile Folgendes ein, um den einheitlichen Kontaktspeicher für einzelne Benutzer zu deaktivieren:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Beispiel:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Bevor Sie einen Benutzer aus lync Server 2013 in lync Server 2010 verschieben, führen Sie ein Rollback der Buddyliste für die angegebenen Benutzer in lync Server aus.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn dieser Schritt ausgelassen wird, geht die Buddy-Liste verloren.

    
    </div>

4.  Führen Sie ein Rollback für die angegebenen Benutzer aus. Geben Sie an der Befehlszeile Folgendes ein:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Beispiel:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Es wird davon abgeraten, mit der Option –Force das Rollback zu erzwingen. Falls Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>So setzen Sie die Kontakte für den einheitlichen Kontaktspeicher von Exchange 2013 auf lync Server 2013 zurück

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Deaktivieren Sie den einheitlichen Kontaktspeicher für die Benutzer, für die ein Rollback ausgeführt werden soll, damit sie nach dem Rollback nicht erneut migriert werden. Geben Sie an der Befehlszeile Folgendes ein, um den einheitlichen Kontaktspeicher für einzelne Benutzer zu deaktivieren:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Beispiel:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Führen Sie ein Rollback für die angegebenen Benutzer aus. Geben Sie an der Befehlszeile Folgendes ein:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Beispiel:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen zuerst den lync Server Benutzer zurücksetzen und dann das Exchange 2013 Postfach bewegen. Dem Exchange-Administrator wird das Zurücksetzen von Exchange bis zum Abschluss des lync Server Rollbacks blockiert. Es wird davon abgeraten, mit der Option –Force das Rollback zu erzwingen. Falls Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.

    
    </div>

4.  Nachdem Sie den Benutzer auf lync Server zurückgesetzt haben, kann der Exchange-Administrator den Exchange-Benutzer von Exchange 2013 auf Exchange 2010 zurücksetzen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

