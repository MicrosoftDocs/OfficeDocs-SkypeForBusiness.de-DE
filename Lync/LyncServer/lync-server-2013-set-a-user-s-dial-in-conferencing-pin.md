---
title: 'Lync Server 2013: Festlegen der Einwahlkonferenz-PIN eines Benutzers'
TOCTitle: Festlegen der Einwahlkonferenz-PIN eines Benutzers
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520985(v=OCS.15)
ms:contentKeyID: 49293821
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Festlegen der Einwahlkonferenz-PIN eines Benutzers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-06-10_

Zur Teilnahme an einer Einwahlkonferenz als authentifizierter Benutzer benötigt ein Lync Server 2013-Benutzer mit AD DS-Anmeldeinformationen (Active Directory Domain Services, Active Directory-Domänendienste) eine persönliche Identifikationsnummer (PIN). Wenn ein Benutzer die PIN für die Einwahlkonferenz vergisst oder nicht über Lync Server festgelegt hat, können Sie die PIN des Benutzers über die Lync Server-Systemsteuerung festlegen. Die PIN kann entweder automatisch generiert oder manuell erstellt werden.


> [!NOTE]
> Bestimmte Eigenschaften der PIN, beispielsweise die Mindestlänge, können als Richtlinie konfiguriert werden. Zusätzlich zur globalen Richtlinie können Sie eine PIN-Richtlinie für einzelne Standorte oder Benutzer konfigurieren. Ausführliche Informationen zur Konfiguration einer PIN-Richtlinie finden Sie unter <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Konfigurieren von PIN-Regeln (persönliche Identifikationsnummer) für Einwahlkonferenzen in Lync Server 2013</A>.



## So legen Sie die PIN für einen Benutzer fest

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** .

4.  Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
      - Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen** .
    
      - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen** , verwenden Sie das Dialogfeld **Öffnen** , um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen** .

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:
    
    1.  Klicken Sie auf **Filter hinzufügen** .
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich** ).
    
    4.  Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.
        

        > [!TIP]
        > Klicken Sie auf <STRONG>Filter hinzufügen</STRONG> , um zusätzliche Suchklauseln einzugeben.

    
    5.  Klicken Sie auf **Suchen** .
    

    > [!NOTE]
    > Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf <STRONG>Aktion</STRONG> und auf <STRONG>PIN entsperren</STRONG> .



6.  Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN festlegen** .

7.  Führen Sie im Dialogfeld **PIN festlegen** einen der folgenden Schritte aus:
    
      - Wählen Sie **Gültige PIN automatisch generieren** , um das Generieren der PIN eines Benutzers durch Lync Server 2013 zuzulassen (Standardeinstellung).
    
      - Zum Erstellen einer eigenen PIN klicken Sie auf **Bestimmte PIN manuell eingeben** , klicken Sie auf das Textfeld, und geben Sie anschließend eine PIN ein, welche die in Ihren PIN-Richtlinieneinstellungen angegebenen PIN-Anforderungen erfüllt.

8.  Klicken Sie auf **OK** .

9.  Führen Sie im Abschnitt **PIN festlegen** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **PIN anzeigen** , um die PIN anzuzeigen, kopieren Sie die PIN, und teilen Sie sie dem Benutzer über die bevorzugte Methode Ihrer Organisation mit.
    
      - Klicken Sie auf **E-Mail-Anwendung zum Senden der neuen PIN an den Benutzer öffnen** , um die PIN per E-Mail zu senden. Wenn Sie Microsoft Office Outlook als E-Mail-Client verwenden, wird die PIN automatisch in die neue E-Mail-Nachricht kopiert. Wenn Sie einen anderen E-Mail-Client einsetzen, aktivieren Sie das Kontrollkästchen **PIN anzeigen** , und kopieren Sie die PIN anschließend in die E-Mail-Nachricht.

10. Klicken Sie auf **Schließen** .

## Zuweisen einer Benutzer-PIN mithilfe von Windows PowerShell-Cmdlets

Sie können Benutzern mithilfe des Cmdlets Lock-Set-CsClientPin PINs zuweisen. Sie können dieses Cmdlet entweder aus dem Verwaltungsshell für Lync Server 2013 oder aus einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So weisen Sie Benutzern automatisch PINs zu

  - Der folgende Befehl weist dem Benutzer Ken Myer eine PIN zu. Da der PIN-Parameter nicht eingeschlossen ist, erstellt Lync Server die PIN automatisch und weist sie zu.
    
        Set-CsClientPin -Identity "Ken Myer" 

## So weisen Sie einem Benutzer eine bestimmte PIN zu

  - Der folgende Befehl verwendet den PIN-Parameter, um dem Benutzer Ken Myer die PIN 121989 zuzuweisen.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

Weitere Informationen finden Sie in dem Hilfethema zum [Set-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPin)-Cmdlet.

## Siehe auch

#### Konzepte

[Zugriffsnummer für Einwahlkonferenz](https://technet.microsoft.com/de-de/library/gg133674\(v=ocs.15\))  

#### Weitere Ressourcen

[Konfigurieren von PIN-Regeln (persönliche Identifikationsnummer) für Einwahlkonferenzen in Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)

