---
title: Anzeigen von Informationen zu Benutzer-PINs
TOCTitle: Anzeigen von Informationen zu Benutzer-PINs
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49890759
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Benutzer-PINs

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Um einer Einwahlkonferenz als authentifizierter Benutzer beizutreten, benötigt ein Lync Server 2013-Benutzer mit Anmeldeinformationen für die Active Directory-Domänendienste (Active Directory Domain Services, AD DS) eine persönliche Identifikationsnummer (PIN). Sie können die PIN-Informationen eines Benutzers über die Systemsteuerung für Lync Server 2013 anzeigen.


> [!NOTE]
> Sie können verschiedene PIN-Statusinformationen anzeigen. Dazu gehört u. a. ob eine PIN festgelegt wurde oder wann die PIN zum letzten Mal geändert wurde. Die aktuelle PIN wird beim Betrachten des PIN-Status jedoch nicht angezeigt. Wenn ein Benutzer seine PIN verloren hat, kann diese mit den in <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Festlegen der Einwahlkonferenz-PIN eines Benutzers in Lync Server 2013</A> beschriebenen Verfahren zurückgesetzt werden.



## So zeigen Sie die PIN eines Benutzers in Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Suchen Sie mit einer der folgenden Methoden nach dem Benutzer:
    
      - Geben Sie im Feld **Benutzer suchen** den Anzeigenamen, den Vornamen, den Nachnamen, den SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder die Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos teilweise oder vollständig ein, und klicken Sie auf **Suchen**.
    
      - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**. Anschließend rufen Sie die Abfrage (eine USF-Datei) mithilfe des Dialogfelds **Öffnen** ab und klicken auf **Suchen**.

5.  (Optional) Geben Sie weitere Kriterien ein, um die Suchergebnisse einzuschränken:
    
    1.  Klicken Sie auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, oder wählen Sie sie aus der Dropdownliste aus.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf den Operator (z. B. **Gleich** oder **Ungleich**).
    
    4.  Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.
        

        > [!TIP]
        > Um Ihrer Abfrage weitere Suchklauseln hinzuzufügen, klicken Sie auf <STRONG>Filter hinzufügen</STRONG>.

    
    5.  Klicken Sie auf **Suchen**.
    

    > [!NOTE]
    > Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf <STRONG>Aktion</STRONG> und auf <STRONG>PIN entsperren</STRONG>.



6.  Klicken Sie auf einen Benutzer in den Suchergebnissen und dann auf **Aktion** und auf **PIN-Status anzeigen**.

## So zeigen Sie die PIN-Informationen für Benutzer mit den Lync Server-Verwaltungsshell-Cmdlets an

Sie können die PIN-Informationen für Benutzer mit dem Get-CsClientPinInfo-Cmdlet anzeigen. Dieses Cmdlet kann in der Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie die PIN-Informationen von Benutzern an

  - Um die PIN-Informationen eines Benutzers anzuzeigen, geben Sie einen Befehl wie den folgenden in der Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Dadurch werden Informationen ähnlicher der folgenden zurückgegeben:
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

Weitere Informationen finden Sie im Hilfethema zum [Get-CsConferenceDisclaimer](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferenceDisclaimer)-Cmdlet.

## Siehe auch

#### Aufgaben

[Festlegen der Einwahlkonferenz-PIN eines Benutzers in Lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Sperren oder Entsperren einer Benutzer-PIN](lync-server-2013-lock-or-unlock-a-user-pin.md)

