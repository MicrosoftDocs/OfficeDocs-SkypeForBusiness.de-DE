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
ms.openlocfilehash: 5e8b8c53f835bbbaa363a91ef547dd1d301c8976
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>Zurücksetzen von migrierten Benutzern in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-07_

Wenn Sie die Unified Contact Store-Funktion zurücksetzen müssen, setzen Sie die Kontakte nur zurück, wenn Sie den Benutzer wieder in Exchange 2010 oder lync Server 2010 zurück bewegen. Zum Zurücksetzen des Rollbacks deaktivieren Sie die Richtlinie für den Benutzer, und führen Sie dann das Cmdlet **Invoke-CsUcsRollback** aus. Nur die Ausführung von **Invoke-CsUcsRollback** allein reicht nicht aus, um einen dauerhaften Rollback zu gewährleisten, da die Migration von Unified Contact Store erneut initiiert wird, wenn die Richtlinie nicht deaktiviert ist. Wenn ein Benutzer beispielsweise zurückgesetzt wird, weil Exchange 2013 auf Exchange 2010 zurückgesetzt wird und dann das Postfach des Benutzers in Exchange 2013 verschoben wird, wird die Unified Contact Store-Migration sieben Tage nach dem Rollback erneut initiiert, solange der Unified Contact Store ist in der Richtlinie für Benutzer Dienste weiterhin für den Benutzer aktiviert.

<div>


> [!IMPORTANT]  
> Mit dem Cmdlet <STRONG>Move-CsUser</STRONG> wird in den folgenden Situationen automatisch der Kontaktspeicher des Benutzers von Exchange 2013 auf lync Server 2013 zurückgesetzt: 
> <UL>
> <LI>
> <P>Wenn Benutzer von lync Server 2013 auf lync Server 2010 verschoben werden.</P>
> <LI>
> <P>Wenn Benutzer über einen Standort migriert werden, beispielsweise wenn ein Benutzer von lync online zu lync Server 2013 lokal oder umgekehrt verschoben wird.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel: 
> <UL>
> <LI>
> <P>Wenn Sie Kontaktlisten exportieren, bevor die Kontakte der Benutzer nach Exchange 2013 migriert werden, und dann nach der Migration dieselben Daten importieren, werden die Unified Contact Store-Daten und Kontaktlisten beschädigt.</P>
> <LI>
> <P>Wenn Sie Benutzerdaten nach dem Migrieren von Benutzern zu Exchange 2013 exportieren, führen Sie eine Rollback für die Migration aus, und importieren Sie dann aus irgendeinem Grund die Daten aus der nach der Migration, werden die Unified Contact Store-Daten und Kontaktlisten beschädigt.</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> Bevor Sie ein Exchange-Postfach von Exchange 2013 auf Exchange 2010 verschieben, muss der Exchange-Administrator sicherstellen, dass der lync Server-Administrator zuerst die lync Server-Benutzer Kontakte von Exchange 2013 auf lync Server zurückgesetzt hat. Informationen zum Rollback von Unified Contact Store-Kontakten zu lync Server finden Sie unter Verfahren "So führen Sie einen Rollback für Unified Contact Store-Kontakte von Exchange 2013 zu lync Server 2013" weiter unten in diesem Abschnitt durch.



</div>

Im folgenden Verfahren wird beschrieben, wie Sie ein Rollback für Benutzerkontakte ausführen. Wenn Sie das Cmdlet **Move-CsUser** verwenden, um Benutzer zwischen lync Server 2013 und lync Server 2010 zu verschieben, können Sie diese Schritte überspringen, da das Cmdlet **Move-CsUser** automatisch unifed Kontaktspeicher zurücksetzt, wenn Benutzer von lync Server 2013 nach lync Server 2010 verschoben werden. **Verschieben-CsUser** deaktiviert die Unified Contact Store-Richtlinie nicht, sodass die Migration in den Unified Contact Store wiederholt wird, wenn der Benutzer zurück zu lync Server 2013 verschoben wird.

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>So führen Sie einen Rollback für Benutzer Kontakte von lync Server 2013 auf lync Server 2010 aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Deaktivieren Sie den einheitlichen Kontaktspeicher, damit die Benutzer zurückgesetzt werden können, damit Sie nach dem Rollback nicht erneut migriert werden. (Führen Sie diesen Schritt nur aus, wenn Sie sicherstellen möchten, dass Benutzer in Zukunft nicht mehr migriert werden.) Wenn Sie den Unified Contact Store für einzelne Benutzer deaktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Beispiel:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Bevor Sie einen Benutzer von lync Server 2013 auf lync Server 2010 verschieben, können Sie die Kontaktliste für die angegebenen Benutzer auf dem lync-Server wiederherstellen.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn dieser Schritt ausgelassen wird, geht die Kontaktliste verloren.

    
    </div>

4.  Wiederherstellen der angegebenen Benutzer Geben Sie in der Befehlszeile Folgendes ein:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Beispiel:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Es wird nicht empfohlen, die Option – Force zu verwenden, um das Rollback zu erzwingen. Wenn Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>So führen Sie einen Rollback für Unified Contact Store-Kontakte von Exchange 2013 auf lync Server 2013 aus

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Deaktivieren Sie den einheitlichen Kontaktspeicher, damit die Benutzer zurückgesetzt werden können, damit Sie nach dem Rollback nicht erneut migriert werden. Wenn Sie den Unified Contact Store für einzelne Benutzer deaktivieren möchten, geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    Beispiel:
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  Wiederherstellen der angegebenen Benutzer Geben Sie in der Befehlszeile Folgendes ein:
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    Beispiel:
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > Sie müssen zunächst den lync Server-Benutzer zurücksetzen und dann das Exchange 2013-Postfach verschieben. Der Exchange-Administrator ist vom Rollback von Exchange blockiert, bis der lync Server-Rollback abgeschlossen ist. Es wird nicht empfohlen, die Option – Force zu verwenden, um das Rollback zu erzwingen. Wenn Sie diese Option verwenden, gehen die Kontakte der Benutzer verloren.

    
    </div>

4.  Nachdem Sie den Benutzer auf lync Server zurückgesetzt haben, kann der Exchange-Administrator den Exchange-Benutzer von Exchange 2013 auf Exchange 2010 zurücksetzen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

