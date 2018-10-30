---
title: Erstellen oder Ändern einer Ortungsrichtlinie
TOCTitle: Erstellen oder Ändern einer Ortungsrichtlinie
ms:assetid: 10338418-4da4-42df-b231-f52098c08dae
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687971(v=OCS.15)
ms:contentKeyID: 49890627
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Ortungsrichtlinie

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In Lync Server 2013 können Sie mit der Ortungsrichtlinie Einstellungen im Zusammenhang mit der Funktion "9-1-1 (erweitert) (E9-1-1)" und den Standorteinstellungen für Benutzer oder Kontakte zuweisen. Die Ortungsrichtlinie ermittelt, ob E9-1-1 für einen Benutzer aktiviert ist, und legt ggf. das Verhalten eines Notrufs fest. Sie können mit der Ortungsrichtlinie beispielsweise definieren, welche Nummer als Notrufnummer betrachtet wird (z. B. 911), ob die Abteilung für Unternehmenssicherheit automatisch benachrichtigt und wie der Anruf weitergeleitet werden soll.

Sie können Ortungsrichtlinien in der Systemsteuerung für Lync Server 2013 in der Gruppe **Netzwerkkonfiguration** konfigurieren. In der Lync Server-Systemsteuerung können Ortungsrichtlinien angezeigt, erstellt, geändert und gelöscht werden. Verwenden Sie die Verfahren in diesem Abschnitt, um eine Ortungsrichtlinie zu erstellen oder zu ändern. Nähere Informationen zum Löschen von Ortungsrichtlinien finden Sie unter [Löschen einer Ortungsrichtlinie](lync-server-2013-deleting-a-location-policy.md).

In Lync Server 2013 können Sie den Standardzeitraum zwischen Clientanfragen nach einer Ortungsaktualisierung durch den Standortinformationsdienst außer Kraft setzen. -der Standardwert ist 4 Stunden. Verwenden Sie das Cmdlet **Set-CsLocationPolicy** mit dem Parameter "LocationRefreshInterval", um den Standardwert außer Kraft zu setzen.

## So erstellen Sie in Lync Server-Systemsteuerung eine neue Ortungsrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf **Neu**, und wählen Sie den gewünschten Richtlinientyp aus:
    
      - Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Wählen Sie in **Standort auswählen** den Standort aus, auf den die Richtlinie angewendet werden soll, und klicken Sie auf **OK**. Auf der Seite **Neue Ortungsrichtlinie** enthält das Feld **Gültigkeitsbereich** den Wert **Standort**, das Feld **Name** den Namen des gewählten Standorts. Diese beiden Felder können nicht geändert werden. Eine Ortungsrichtlinie wird automatisch auf alle Benutzer am angegebenen Standort angewendet, und die globale Richtlinie wird für diese Benutzer außer Kraft gesetzt.
    
      - Klicken Sie auf **Benutzerrichtlinie**, um eine Richtlinie auf Benutzerbasis zu erstellen. Auf der Seite **Neue Ortungsrichtlinie** enthält das Feld **Gültigkeitsbereich** den Wert **Benutzer**. Dieser Wert kann nicht geändert werden. Geben Sie im Feld **Name** den Namen ein, den Sie dieser Richtlinie zuweisen möchten. Eine Benutzerrichtlinie wird nicht automatisch auf einen Benutzer angewendet. Nach dem Erstellen der Benutzerrichtlinie muss die Richtlinie manuell den Benutzern oder Netzwerkstandorten zugeordnet werden, auf die die Richtlinie angewendet werden soll.

5.  Treffen Sie für die übrigen Felder die folgende Auswahl:
    
      - **Notrufunterstützungsdienste aktivieren**   Aktivieren Sie dieses Kontrollkästchen, um die dieser Richtlinie zugeordneten Benutzer für E9-1-1 zu aktivieren. Bei aktivierter Notrufunterstützung rufen Lync Server-Clients die Ortungsinformationen zur Registrierung ab und berücksichtigen diese Informationen, wenn ein Notruf abgesetzt wird.
    
      - **Standort** Geben Sie einen der folgenden Werte an:
        
          - **Erforderlich** Der Benutzer wird zur Eingabe von Standortinformationen aufgefordert, wenn der Client sich an einem neuen Standort registriert. Der Benutzer kann die Eingabeaufforderung ohne Eingabe von Informationen verwerfen. Wenn Informationen eingegeben werden, wird ein Notruf zur Überprüfung des Standorts zunächst vom Anbieter für die Notrufunterstützung angenommen, bevor er an die Rettungsleitstelle weitergeleitet wird.
        
          - **Nicht erforderlich** Der Benutzer wird nicht zur Eingabe eines Standorts aufgefordert. Wird ein Anruf ohne Standortinformationen getätigt, nimmt der Anbieter für die Notrufunterstützung den Anruf entgegen und fragt nach dem Standort.
        
          - **Haftungsausschluss**   Diese Option entspricht der Option **Diese Option entspricht der Option**; allerdings kann der Benutzer die Eingabeaufforderung nicht ohne Eingabe der Standortinformationen verwerfen. Der Benutzer kann zwar einen Notruf absetzen, es können jedoch ohne Eingabe der Informationen keine weiteren Anrufe getätigt werden. Außerdem wird dem Benutzer ein Haftungsausschluss angezeigt, der ihn auf die möglichen Folgen hinweist, wenn er keine Standortinformationen eingibt. Zum Festlegen des Haftungsausschlusstexts müssen Sie mithilfe der Lync Server-Verwaltungsshell das Cmdlet **Set-CsLocationPolicy** oder **New-CsLocationPolicy** mit dem Parameter "EnhancedEmergencyServiceDisclaimer" auszuführen. Ausführliche Informationen finden Sie unter [Set-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsLocationPolicy) oder [New-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsLocationPolicy) in der Lync Server-Verwaltungsshell-Dokumentation.
            

            > [!NOTE]
            > In Lync Server 2013 können Sie eine Ortungsrichtlinie zum Festlegen verschiedener Haftungsausschlüsse für verschiedene Gebietschemas oder Benutzersätze verwenden. In Lync Server 2010 war dagegen nur das Festlegen eines globalen Haftungsauschlusses für die gesamte Organisation möglich.

    
      - **Standort nur für Notrufdienste verwenden**   Lync kann Standortinformationen für verschiedene Zwecke verwenden (z. B. zur Benachrichtigung von Teammitgliedern über Ihren aktuellen Standort). Aktivieren Sie dieses Kontrollkästchen, um sicherzustellen, dass Standortinformationen nur für einen Notruf zur Verfügung stehen.
    
      - **PSTN-Verwendung** Die Festnetz (Public Switched Telephone Network, PSTN)-Verwendung zur Bestimmung der VoIP-Route, die zum Weiterleiten von Notrufen von Clients eingesetzt wird, die dieses Profil verwenden. Die dieser Verwendung zugeordnete Route muss auf einen SIP-Trunk verweisen, der speziell für Notrufe eingerichtet wurde, oder auf ein ELIN (Emergency Location Identification Number)-Gateway, das den Notruf an die nächstgelegene Rettungsleitstelle weiterleitet.
    
      - **Notrufnummer**   Die Nummer, die zum Erreichen der Notrufdienste gewählt wird. In den USA lautet dieser Wert 911. Die Zeichenfolge muss aus den Ziffern 0 bis 9 bestehen und kann 1 bis 10 Ziffern umfassen.
    
      - **Notrufmaske**   Eine Nummer, die in den Wert der Notrufnummer übersetzt wird, wenn sie gewählt wird. Wenn Sie in diesem Feld beispielsweise den Wert 212 eingeben und das Feld mit der Notrufnummer den Wert 911 aufweist, wird automatisch ein Notruf abgesetzt, wenn ein Benutzer 212 wählt. Auf diese Weise können andere Notrufnummern eingerichtet werden, die dennoch die Notrufdienste erreichen. (Dies ist beispielsweise hilfreich, wenn jemand aus einem Land oder einer Region mit einer anderen Notrufnummer versucht, die Notrufnummer des eigenen Landes zu wählen und nicht die Notrufnummer des Landes oder der Region, in dem/der er sich gerade aufhält.) Um mehrere Notrufmasken zu definieren, trennen Sie die Werte durch ein Semikolon. Beispiel: 212;414. Die maximale Länge der Zeichenfolge beträgt 100 Zeichen. Bei jedem Zeichen muss es sich um eine Ziffer von 0 bis 9 handeln.
        

        > [!IMPORTANT]
        > Stellen Sie sicher, dass die angegebenen Notrufmaskenwerte nicht mit einer Nummer im Bereich eines Orbits zum Parken von Anrufen übereinstimmen. Die Weiterleitung zum Parken von Anrufen hat Vorrang vor der Konvertierung von Notrufwählzeichenfolgen. Klicken Sie in der linken Navigationsleiste auf <STRONG>VoIP-Funktionen</STRONG> und dann auf <STRONG>Anruf parken</STRONG>, um die vorhandenen Orbitbereiche für das Parken von Anrufen anzuzeigen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-phone-number-extensions-for-parking-calls.md">Konfigurieren von Durchwahlnummern für das Parken von Anrufen</A>.

    
      - **Benachrichtigungs-URI**   Ein oder mehrere SIP-URIs (Uniform Resource Identifier), die beim Absetzen eines Notrufs benachrichtigt werden sollen. Beispielsweise kann die Sicherheitsstelle des Unternehmens durch eine Sofortnachricht über jeden Notruf informiert werden. Wenn der Anruferstandort verfügbar ist, wird dieser Standort in die Benachrichtigung aufgenommen. Es können mehrere SIP-URIs als eine durch Trennzeichen getrennte Liste eingeschlossen werden. Beispiel: "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". Verteilerlisten werden nicht unterstützt. Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Bevor Sie in das Feld für den Benachrichtigungs-URI klicken, wird ein Beispiel angezeigt.
    
      - **Konferenz-URI**   Der SIP-URI, in diesem Fall die Telefonnummer, eines dritten Teilnehmers, der bei allen abgesetzten Notrufen zugeschaltet wird. Beispielsweise kann die Sicherheitsstelle des Unternehmens beim Absetzen eines Notrufs einen Anruf erhalten und den Anruf abhören oder daran teilnehmen (je nach Wert des Felds **Konferenzmodus**). Die Zeichenfolge muss zwischen 1 und 256 Zeichen lang sein und mit dem Präfix "sip:" beginnen. Bis Sie in dieses Feld klicken, wird ein Beispiel angezeigt.
    
      - **Konferenzmodus** Wenn Sie im Feld **Konferenz-URI** einen Wert angeben, wird über den **Konferenzmodus** festgelegt, ob ein dritter Teilnehmer den Anruf abhören oder daran teilnehmen kann. Wählen Sie eine der folgenden Optionen aus:
        
          - **Unidirektional**   Ein dritter Teilnehmer kann die Unterhaltung zwischen dem Anrufer und der Rettungsleitstelle nur hören.
        
          - **Bidirektional** Ein dritter Teilnehmer kann die Unterhaltung zwischen dem Anrufer und der Rettungsleitstelle hören und daran teilnehmen.

6.  Klicken Sie auf **Commit**.
    

    > [!IMPORTANT]
    > Beim Erstellen einer Benutzerrichtlinie wird die Richtlinie zunächst nicht auf Benutzer oder Netzwerkstandorte angewendet. Zum Anwenden der Richtlinie auf einen Benutzer klicken Sie in der linken Navigationsleiste auf <STRONG>Benutzer</STRONG>. Suchen Sie nach dem Benutzer, dem die Richtlinie zugewiesen werden soll. Klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>. Wählen Sie auf der Seite <STRONG>Lync Server-Benutzer bearbeiten</STRONG> in der Dropdownliste <STRONG>Ortungsrichtlinie</STRONG> die neue Ortungsrichtlinie aus, und klicken Sie auf <STRONG>Commit</STRONG>.<BR>Zum Zuweisen der Richtlinie zu einem Netzwerkstandort klicken Sie in der linken Navigationsleiste auf <STRONG>Netzwerkkonfiguration</STRONG> und anschließend auf <STRONG>Standort</STRONG>. Suchen Sie nach dem Netzwerkstandort, dem die Richtlinie zugewiesen werden soll. Klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG>. Wählen Sie in <STRONG>Standort bearbeiten</STRONG> in der Dropdownliste <STRONG>Ortungsrichtlinie</STRONG> die neue Ortungsrichtlinie aus, und klicken Sie auf <STRONG>Commit</STRONG>.



## So ändern Sie in Lync Server-Systemsteuerung eine Ortungsrichtlinie

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Ortungsrichtlinie**.

4.  Klicken Sie auf der Seite **Ortungsrichtlinie** auf die Ortungsrichtlinie, die geändert werden soll.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Ändern Sie auf der Seite **Ortungsrichtlinie bearbeiten** die gewünschten Felder (ausführliche Informationen finden Sie in Schritt 5 unter "So erstellen Sie eine neue Ortungsrichtlinie" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit**.

## Siehe auch

#### Aufgaben

[Löschen einer Ortungsrichtlinie](lync-server-2013-deleting-a-location-policy.md)  

#### Konzepte

[Definieren der Standortrichtlinie für Lync Server 2013](lync-server-2013-defining-the-location-policy.md)  

#### Weitere Ressourcen

[Konfigurieren von Durchwahlnummern für das Parken von Anrufen](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

