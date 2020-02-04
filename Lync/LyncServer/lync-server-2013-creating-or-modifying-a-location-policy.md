---
title: 'Lync Server 2013: Erstellen oder Ändern einer Standortrichtlinie'
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
ms.openlocfilehash: 1648e845fc3759e7083c2443013f89fb49c1b00f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-a-location-policy-in-lync-server-2013"></a>Erstellen oder Ändern einer Standortrichtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In lync Server 2013 können Sie mithilfe der ortungsrichtlinie Einstellungen anwenden, die sich auf die erweiterte 9-1-1 (E9-1-1)-Funktionalität und auf die Standorteinstellungen für Benutzer oder Kontakte beziehen. Die ortungsrichtlinie bestimmt, ob ein Benutzer für E9-1-1 aktiviert ist, und wenn ja, was das Verhalten eines Notrufs ist. So können Sie beispielsweise mithilfe der ortungsrichtlinie definieren, welche Nummer ein Notruf ist (beispielsweise 911 in den USA), ob die Unternehmenssicherheit automatisch benachrichtigt werden soll und wie der Anruf weitergeleitet werden soll.

Sie können Standortrichtlinien über die Gruppe **Netzwerkkonfiguration** in der lync Server 2013-Systemsteuerung konfigurieren. In der lync Server-Systemsteuerung können Sie Positions Richtlinien anzeigen, erstellen, ändern oder löschen. Verwenden Sie die Verfahren in diesem Abschnitt, um eine Standortrichtlinie zu erstellen oder zu ändern. Details zum Löschen von Standortrichtlinien finden Sie unter [Löschen einer Standortrichtlinie in lync Server 2013](lync-server-2013-deleting-a-location-policy.md).

In lync Server 2013 können Sie die Standardzeit Spanne zwischen Clientanforderungen für ein Standort Update über den standortinformationsdienst außer Kraft setzen. Der Standardwert ist 4 Stunden. Verwenden Sie das Cmdlet " **Satz-CsLocationPolicy** " mit dem Parameter LocationRefreshInterval, um den Standardwert zu überschreiben.

<div>

## <a name="to-create-a-new-location-policy-in-lync-server-control-panel"></a>So erstellen Sie eine neue Standortrichtlinie in der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Standortrichtlinie** auf **neu** , und wählen Sie dann den Typ der zu erstellenden Richtlinie aus:
    
      - Wenn Sie eine Website Richtlinie erstellen möchten, klicken Sie auf **Website Richtlinie**. Wählen Sie unter **Website auswählen**die Website aus, auf die die Richtlinie angewendet werden soll, und klicken Sie auf **OK**. Auf der Seite " **neue Standortrichtlinie** " enthält das Feld " **Bereich** " die Wert **Website**, und das Feld " **Name** " enthält den Namen der Website, die Sie ausgewählt haben. Beide Felder können nicht geändert werden. Eine Website Richtlinie wird automatisch auf alle Benutzer der angegebenen Website angewendet und überschreibt die globale Richtlinie für diese Benutzer.
    
      - Klicken Sie zum Erstellen einer **Benutzer**Richtlinie auf **Benutzerrichtlinie**. In der **Richtlinie für neue Standorte**enthält das Feld **Scope** den Wert **Benutzer**. Dieser Wert kann nicht geändert werden. Geben Sie im Feld **Name** den Namen ein, den Sie dieser Richtlinie zuweisen möchten. Eine Benutzerrichtlinie gilt nicht automatisch für alle Benutzer. Nachdem Sie die Benutzerrichtlinie erstellt haben, müssen Sie die Richtlinie den Benutzern oder Netzwerk Websites, auf die Sie die Richtlinie anwenden möchten, manuell erteilen.

5.  Füllen Sie die restlichen Felder wie folgt aus:
    
      - **Aktivieren von erweiterten Notfalldiensten**   aktivieren Sie dieses Kontrollkästchen, um die Benutzer zu aktivieren, die dieser Richtlinie für E9-1-1 zugeordnet sind. Wenn Notfalldienste aktiviert sind, rufen lync Server-Clients Standortinformationen bei der Registrierung ab und schließen diese Informationen bei einem Notruf ein.
    
      - **Ort**   geben Sie einen der folgenden Werte an:
        
          - **Erforderlich**   der Benutzer wird aufgefordert, Standortinformationen einzugeben, wenn sich der Client an einem neuen Speicherort registriert. Der Benutzer kann die Eingabeaufforderung ohne Angabe von Informationen schließen. Wenn Informationen eingegeben werden, wird zuerst ein Notruf vom Notrufdienst Anbieter beantwortet, um den Standort zu verifizieren, bevor er an den PSAP-Operator (Public Safety Answering Point) weitergeleitet wird (also an den 911-Operator).
        
          - **Nicht erforderlich**   der Benutzer wird nicht zur Eingabe eines Speicherorts aufgefordert. Wenn ein Anruf ohne Standortinformationen erfolgt, wird der Notfalldienst Anbieter den Anruf annehmen und einen Standort anfordern.
        
          - **Haftungsausschluss**   diese Option ist wie **erforderlich** , mit der Ausnahme, dass der Benutzer die Eingabeaufforderung nicht schließen kann, ohne Standortinformationen einzugeben. Der Benutzer kann weiterhin einen Notruf durchführen, aber keine weiteren Anrufe können ohne Eingabe der Informationen abgeschlossen werden. Darüber hinaus wird dem Benutzer ein Haftungsausschluss Text angezeigt, der Sie auf die Folgen aufmerksam machen kann, die zum Eingeben von Standortinformationen in Frage kommen. Um den Haftungsausschluss Text einzurichten, müssen Sie die lync Server-Verwaltungsshell verwenden, um das Cmdlet " **CsLocationPolicy** " oder das Cmdlet " **New-CsLocationPolicy** " mit dem EnhancedEmergencyServiceDisclaimer-Parameter auszuführen. Ausführliche Informationen finden Sie unter " [CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) " oder " [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy) " in der Dokumentation zur lync Server-Verwaltungsshell.
            
            <div>
            

            > [!NOTE]  
            > In lync Server 2013 können Sie mithilfe der ortungsrichtlinie verschiedene Haftungsausschlüsse für verschiedene Gebietsschemas oder verschiedene Benutzergruppen festlegen, anders als in lync Server 2010, in dem Sie nur einen globalen Haftungsausschluss für die gesamte Organisation angeben könnten.

            
            </div>
    
      - **Verwenden des Standorts für Notfalldienste nur**   lync kann Standortinformationen aus verschiedenen Gründen verwenden (beispielsweise um Teamkollegen von Ihrem aktuellen Standort zu benachrichtigen). Aktivieren Sie dieses Kontrollkästchen, um sicherzustellen, dass die Standortinformationen nur zur Verwendung mit einem Notruf zur Verfügung stehen.
    
      - **PSTN-Nutzung**   die Nutzung des öffentlich geschalteten Telefonnetzwerks (PSTN), die verwendet wird, um festzustellen, welche VoIP-Route für die Weiterleitung von Notrufen von Kunden mit diesem Profil verwendet wird. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet.
    
      - **Notrufnummer**   die Nummer, die gewählt wird, um Notfalldienste zu erreichen. In den Vereinigten Staaten ist dieser Wert 911. Die Zeichenfolge muss aus den Ziffern 0 bis 9 bestehen und kann zwischen 1 und 10 Ziffern lang sein.
    
      - **Notruf Maske**   eine Nummer, die Sie in den Wert des Notrufnummern Werts übersetzen möchten, wenn Sie gewählt wird. Wenn Sie beispielsweise einen Wert von 212 in dieses Feld eingeben und das Feld für die Notrufnummer einen Wert von 911 hat, wird der Anruf an 911 weitergegeben, wenn ein Benutzer 212 wählt. Auf diese Weise können auch andere Notrufnummern eingerichtet werden, mit denen dennoch die Notrufdienste erreicht werden. (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Landes zu wählen, und nicht die Notrufnummer des Landes oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon, z. B. 212;414. Die maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
        
        <div>
        

        > [!IMPORTANT]  
        > Stellen Sie sicher, dass der angegebene Wähl Maskenwert nicht mit einer Zahl in einem orbitbereich des Anruf Parks identisch ist. Das Routing des Anruf Parks hat Vorrang vor der Notfall Wahl Zeichenfolgenkonvertierung. Klicken Sie in der linken Navigationsleiste auf <STRONG>sprach Features</STRONG> , und klicken Sie dann auf <STRONG>Park anrufen</STRONG>, um die vorhandenen Umlaufbahn Bereiche des Anruf Parks anzuzeigen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Konfigurieren von Telefonnummern Erweiterungen für Park Anrufe in lync Server 2013</A>.

        
        </div>
    
      - **Benachrichtigungs-URI**   eine oder mehrere SIP-Uniform Resource Identifier (URIs), die bei einem Notruf benachrichtigt werden sollen. So könnte beispielsweise das Sicherheitsbüro des Unternehmens durch eine Sofortnachricht benachrichtigt werden, wenn ein Notruf durchgeführt wird. Wenn der Standort des Anrufers verfügbar ist, wird dieser in die Benachrichtigung aufgenommen. Mehrere SIP-URIs können als durch trennzeichengetrennte Liste eingefügt werden. Beispiel: „sip:security@litwareinc.com“,„sip:kmyer@litwareinc.com“. Verteilerlisten werden unterstützt. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix „sip:“ beginnen. Bevor Sie in das Feld "Benachrichtigungs-URI" klicken, wird ein Beispiel angezeigt.
    
      - **Konferenz-URI**   der SIP-URI, in diesem Fall die Telefonnummer eines Drittanbieters, der an allen Notrufen teilnimmt, die getätigt werden. So könnte beispielsweise das Sicherheitsbüro des Unternehmens einen Anruf erhalten, wenn ein Notruf durchgeführt wird, und diesen Anruf anhören oder daran teilnehmen (je nachdem, welcher Wert im Feld **Konferenzmodus** angegeben ist). Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix „sip:“ beginnen. Ein Beispiel wird angezeigt, bis Sie in dieses Feld klicken.
    
      - **Konferenzmodus**   Wenn Sie einen Wert im Feld **Konferenz-URI** angeben, bestimmt der **Konferenzmodus** , ob ein Dritter an dem Anruf teilnehmen oder nur zuhören kann. Geben Sie eine der folgenden Optionen an:
        
          - **Eine**unidirektionale Drittpartei kann nur die Konversation zwischen dem Anrufer und dem PSAP-Operator abhören.   
        
          - **Eine bidirektionale**Drittpartei kann den Anruf zwischen dem Anrufer und dem PSAP-Operator abhören und daran teilnehmen.   

6.  Klicken Sie auf **Commit ausführen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie eine Benutzerrichtlinie erstellen, gilt diese Richtlinie zunächst nicht für Benutzer oder Netzwerk Websites. Wenn Sie die Richtlinie auf einen Benutzer anwenden möchten, klicken Sie in der linken Navigationsleiste auf <STRONG>Benutzer</STRONG> . Suchen Sie den Benutzer, dem Sie die Richtlinie zuweisen möchten. Klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>. Wählen Sie auf der Seite <STRONG>lync Server-Benutzer bearbeiten</STRONG> in der Dropdownliste <STRONG>Standortrichtlinie</STRONG> die neue Standortrichtlinie aus, und klicken Sie dann auf <STRONG>Commit</STRONG>.<BR>Wenn Sie die Richtlinie auf eine Netzwerk Website anwenden möchten, klicken Sie auf der linken Navigationsleiste auf <STRONG>Netzwerkkonfiguration</STRONG> , und klicken Sie dann auf <STRONG>Website</STRONG>. Suchen Sie die Netzwerk Website, auf die Sie die Richtlinie anwenden möchten. Klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>. Wählen Sie auf der <STRONG>Seite "Website bearbeiten</STRONG>" in der Dropdownliste <STRONG>Standortrichtlinie</STRONG> die neue Standortrichtlinie aus, und klicken Sie dann auf <STRONG>Commit</STRONG>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-location-policy-in-lync-server-control-panel"></a>So ändern Sie eine Standortrichtlinie in der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **ortungsrichtlinie**.

4.  Wählen Sie auf der Seite **Standortrichtlinie** die zu ändernde Standortrichtlinie aus.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite " **Standortrichtlinie bearbeiten** " die Felder nach Bedarf (Details finden Sie unter Schritt 5 in den Verfahren zum Erstellen einer neuen Standortrichtlinie weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen einer Standortrichtlinie in lync Server 2013](lync-server-2013-deleting-a-location-policy.md)  


[Definieren der Standortrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md)  


[Konfigurieren von Telefonnummern Erweiterungen für Parken von Anrufen in lync Server 2013](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

