---
title: 'Lync Server 2013: Erstellen oder Ändern einer ortungsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying a location policy
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49733557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60196805cccc13c35d4a4db1aa2ea7ac8e6a9fef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Erstellen oder Ändern einer ortungsrichtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

In lync Server 2013 können Sie die Standortrichtlinie verwenden, um Einstellungen anzuwenden, die sich auf Erweiterte 9-1-1-Funktionen (E9-1-1) und auf Standorteinstellungen für Benutzer oder Kontakte beziehen. Die ortungsrichtlinie legt fest, ob ein Benutzer für E9-1-1 aktiviert ist und was das Verhalten eines Notrufs ist. Beispielsweise können Sie die ortungsrichtlinie verwenden, um zu definieren, welche Zahl einen Notruf darstellt (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.

Sie können Standortrichtlinien in lync Server 2013 Systemsteuerung in der Gruppe " **Netzwerkkonfiguration** " konfigurieren. In lync Server-Systemsteuerung können Sie Standortrichtlinien anzeigen, erstellen, ändern oder löschen. Verwenden Sie die Verfahren in diesem Abschnitt, um eine ortungsrichtlinie zu erstellen oder zu ändern. Ausführliche Informationen zum Löschen von ortungsrichtlinien finden Sie unter [Löschen einer ortungsrichtlinie in lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

In lync Server 2013 können Sie den Standardzeitraum zwischen Clientanforderungen für eine Standortaktualisierung von der Standortinformationsdienst außer Kraft setzen. Der Standardwert ist 4 Stunden. Verwenden Sie das Cmdlet " **CsLocationPolicy** " mit dem Parameter "LocationRefreshInterval", um den Standardwert außer Kraft zu setzen.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>So erstellen Sie eine neue Standortrichtlinie in lync Server-Systemsteuerung

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Standortrichtlinie** auf **neu** , und wählen Sie dann den Typ der Richtlinie aus, die Sie erstellen möchten:
    
      - Klicken Sie zum Erstellen einer Standortrichtlinie auf **Website Richtlinie**. Wählen Sie unter **Standort auswählen**den Standort aus, auf den die Richtlinie angewendet werden soll, und klicken Sie auf **OK**. Auf der Seite **neue Standortrichtlinie** enthält das Feld **Bereich** den Wert **Website**, und das Feld **Name** enthält den Namen der Website, die Sie ausgewählt haben. Beide Felder können nicht geändert werden. Eine Standortrichtlinie wird automatisch auf alle Benutzer des angegebenen Standorts angewendet und setzt die globale Richtlinie für diese Benutzer außer Kraft.
    
      - Klicken Sie zum Erstellen einer **Benutzer**Richtlinie auf **Benutzerrichtlinie**. In der **neuen ortungsrichtlinie**enthält das Feld **Scope** den Wert **User**. Dieser Wert kann nicht geändert werden. Geben Sie in das Feld **Name** den Namen ein, der für diese Richtlinie erteilt werden soll. Eine Benutzerrichtlinie wird nicht automatisch auf alle Benutzer angewendet. Nachdem Sie die Benutzerrichtlinie erstellt haben, müssen Sie die Richtlinie manuell den Benutzern oder Netzwerkstandorten erteilen, auf die die Richtlinie angewendet werden soll.

5.  Füllen Sie die restlichen Felder wie folgt aus:
    
      - **Erweiterte Notfalldienste**   aktivieren aktivieren Sie dieses Kontrollkästchen, um die dieser Richtlinie für E9-1-1 zugeordneten Benutzer zu aktivieren. Wenn Notfalldienste aktiviert sind, werden lync Server Clients Standortinformationen bei der Registrierung abrufen und diese Informationen bei einem Notruf einbinden.
    
      - **Speicherort**   geben Sie einen der folgenden Werte an:
        
          - **Erforderlich**   der Benutzer wird zur Eingabe von Standortinformationen aufgefordert, wenn sich der Client an einem neuen Standort registriert. Der Benutzer kann die Eingabeaufforderung ohne Eingabe von Informationen verwerfen. Wenn Informationen eingegeben werden, wird zuerst ein Notruf vom Anbieter für Notrufdienste beantwortet, um den Standort zu überprüfen, bevor er an den Rettungsleitstelle-Operator (Public Safety Answering Punkt) weitergeleitet wird (der Operator 911).
        
          - **Nicht erforderlich**   der Benutzer wird nicht zur Eingabe eines Speicherorts aufgefordert. Wenn ein Anruf ohne Standortinformationen erfolgt, nimmt der Anbieter für die Notfalldienste den Anruf entgegen und fragt nach einem Standort.
        
          - **Haftungsausschluss**   diese Option **ist identisch mit der Ausnahme,** dass der Benutzer die Eingabeaufforderung nicht schließen kann, ohne Standortinformationen einzugeben. Der Benutzer kann weiterhin einen Notruf abschließen, aber keine weiteren Anrufe können ohne Eingabe der Informationen abgeschlossen werden. Darüber hinaus wird dem Benutzer Haftungsausschluss Text angezeigt, der Sie auf die Folgen einer Ablehnung der Eingabe von Standortinformationen aufmerksam machen kann. Zum Festlegen des Haftungsausschlusses müssen Sie lync Server-Verwaltungsshell verwenden, um das Cmdlet " **CsLocationPolicy** " oder das Cmdlet " **New-CsLocationPolicy** " mit dem Parameter "EnhancedEmergencyServiceDisclaimer" auszuführen. Ausführliche Informationen finden Sie unter [Sets-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) oder [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) in der lync Server-Verwaltungsshell Dokumentation.
            
            <div>
            

            > [!NOTE]  
            > In lync Server 2013 können Sie die ortungsrichtlinie verwenden, um unterschiedliche Haftungsausschlüsse für unterschiedliche Gebietsschemas oder unterschiedliche Benutzergruppen festzulegen, im Gegensatz zu lync Server 2010, in denen Sie nur einen globalen Haftungsausschluss für die gesamte Organisation angeben könnten.

            
            </div>
    
      - **Speicherort für Notfalldienste verwenden nur**   lync kann Standortinformationen aus verschiedenen Gründen verwenden (beispielsweise um Teamkollegen von Ihrem aktuellen Standort zu benachrichtigen). Aktivieren Sie dieses Kontrollkästchen, um sicherzustellen, dass Standortinformationen nur für die Verwendung mit einem Notruf verfügbar sind.
    
      - **PSTN-Verwendung**   die PSTN-Verwendung (Public Switched Telephone Network), die verwendet wird, um zu bestimmen, welche VoIP-Route zum Weiterleiten von Notrufen von Clients verwendet wird, die dieses Profil verwenden. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet.
    
      - **Notrufnummer**   die Nummer, die zum Erreichen der Notrufdienste gewählt wird. In den USA lautet dieser Wert "911". Die Zeichenfolge muss aus den Ziffern 0 bis 9 bestehen und kann 1 bis 10 Ziffern umfassen.
    
      - **Notruf Maske**   eine Nummer, die Sie beim wählen in den Wert des Notrufnummern Werts übersetzen möchten. Wenn Sie beispielsweise den Wert 212 in diesem Feld eingeben und das Feld Notrufnummer den Wert 911 hat, wenn ein Benutzer 212 wählt, wird der Anruf an 911 getätigt. Auf diese Weise können auch andere Notrufnummern eingerichtet werden, mit denen dennoch die Notrufdienste erreicht werden. (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Lands zu wählen, und nicht die Notrufnummer des Lands oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
        
        <div>
        

        > [!IMPORTANT]  
        > Stellen Sie sicher, dass der angegebene Wähl Maskenwert nicht mit einer Zahl in einem orbitbereich für das Parken von Anrufen übereinstimmt. Das Routing von Anruf parken hat Vorrang vor der Konvertierung von Notrufnummern Zeichenfolgen. Um die vorhandenen orbitbereiche für das Parken von Anrufen anzuzeigen, klicken Sie in der linken Navigationsleiste auf <STRONG>VoIP-Funktionen</STRONG> und dann auf <STRONG>Anruf parken</STRONG>. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Konfigurieren von Telefonnummern Erweiterungen für das Parken von Anrufen in lync Server 2013</A>.

        
        </div>
    
      - **Benachrichtigungs-URI**   ein oder mehrere SIP-URIs (Uniform Resource Identifier), die beim Erreichen eines Notrufs benachrichtigt werden sollen. Beispielsweise kann die Sicherheitsstelle des Unternehmens durch eine Chatnachricht über jeden Notruf informiert werden. Wenn der Anruferstandort verfügbar ist, wird dieser Standort in die Benachrichtigung aufgenommen. Mehrere SIP-URIs können als eine durch Trennzeichen getrennte Liste angegeben werden. Beispiel: "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Verteilerlisten werden unterstützt. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Bevor Sie in das Feld Benachrichtigungs-URI klicken, wird ein Beispiel angezeigt.
    
      - **Konferenz-URI**   der SIP-URI, in diesem Fall die Telefonnummer, eines Drittanbieters, der in allen Notrufen, die getätigt werden, an einer Konferenz Teil nimmt. Beispielsweise könnte das Sicherheitsbüro des Unternehmens einen Anruf erhalten, wenn ein Notruf getätigt wird, und diesen Anruf anhören oder daran teilnehmen (abhängig vom Wert, der im Feld **Konferenzmodus** angegeben ist). Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Ein Beispiel wird angezeigt, bis Sie in dieses Feld klicken.
    
      - **Konferenzmodus**   Wenn Sie einen Wert im Feld **Konferenz-URI** angeben, bestimmt der **Konferenzmodus** , ob ein Dritter an dem Anruf teilnehmen oder nur zuhören kann. Geben Sie eine der folgenden Optionen an:
        
          - **Unidirektional**   ein Dritter Teilnehmer kann nur die Unterhaltung zwischen dem Anrufer und dem Rettungsleitstelle-Operator abhören.
        
          - **Zwei-Wege**   -Drittanbieter können den Anruf zwischen dem Anrufer und dem Rettungsleitstelle-Operator abhören und daran teilnehmen.

6.  Klicken Sie auf **Commit ausführen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie eine Benutzerrichtlinie erstellen, gilt diese Richtlinie anfänglich nicht für Benutzer oder Netzwerkstandorte. Wenn Sie die Richtlinie auf einen Benutzer anwenden möchten, klicken Sie in der linken Navigationsleiste auf <STRONG>Benutzer</STRONG> . Suchen Sie nach dem Benutzer, auf den die Richtlinie angewendet werden soll. Klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details einblenden</STRONG>. Wählen Sie auf der Seite <STRONG>Benutzer lync Server bearbeiten</STRONG> in der Dropdownliste <STRONG>Standortrichtlinie</STRONG> die neue Standortrichtlinie aus, und klicken Sie dann auf <STRONG>Commit ausführen</STRONG>.<BR>Klicken Sie auf <STRONG>Netzwerkkonfiguration</STRONG> in der linken Navigationsleiste, und klicken Sie dann auf <STRONG>Website</STRONG>, um die Richtlinie auf einen Netzwerkstandort anzuwenden. Suchen Sie den Netzwerkstandort, auf den die Richtlinie angewendet werden soll. Klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details einblenden</STRONG>. Wählen Sie unter <STRONG>Website bearbeiten</STRONG>die Option neuer ortungsrichtlinie in der Dropdownliste <STRONG>Standortrichtlinie</STRONG> aus, und klicken Sie dann auf <STRONG>Commit</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>So ändern Sie eine ortungsrichtlinie in lync Server-Systemsteuerung

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite **Speicherort Richtlinie bearbeiten** die Felder nach Bedarf (Ausführliche Informationen finden Sie unter Schritt 5 in der Prozedur "So erstellen Sie eine neue Standortrichtlinie" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen einer ortungsrichtlinie in lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Definieren der ortungsrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Konfigurieren von Durchwahlnummern für das Parken von Anrufen in lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

