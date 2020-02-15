---
title: 'Lync Server 2013: Festlegen der PIN eines Benutzers für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c344a848050d53027c094ad549f0285fbae09489
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Festlegen der Einwahlkonferenz-PIN eines Benutzers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-10_

Um an einer Einwahlkonferenz als authentifizierter Benutzer teilzunehmen, benötigt ein lync Server 2013 Benutzer mit Active Directory-Domänendienste (AD DS) Anmeldeinformationen eine persönliche Identifikationsnummer (PIN). Wenn ein Benutzer die PIN für Einwahlkonferenzen vergisst oder die PIN nicht mithilfe von lync Server festgelegt hat, können Sie die PIN des Benutzers aus lync Server-Systemsteuerung festlegen. Die PIN kann entweder automatisch generiert oder manuell erstellt werden.

<div>


> [!NOTE]  
> Bestimmte Eigenschaften der PIN, beispielsweise die Mindestlänge, können als Richtlinie konfiguriert werden. Zusätzlich zur globalen Richtlinie können Sie eine PIN-Richtlinie für einzelne Standorte oder Benutzer konfigurieren. Ausführliche Informationen zum Konfigurieren einer PIN-Richtlinie finden Sie unter <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configure Dial-in Conferencing private Identification Number (PIN) Rules in lync Server 2013</A>.



</div>

<div>

## <a name="to-set-a-users-pin"></a>So legen Sie die PIN für einen Benutzer fest

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
      - Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
    
      - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:
    
    1.  Klicken Sie auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
    4.  Geben Sie je nach ausgewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.
        
        <div>
        

        > [!TIP]  
        > Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.

        
        </div>
    
    5.  Klicken Sie auf **Suchen**.
    
    <div>
    

    > [!NOTE]  
    > Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf <STRONG>Aktion</STRONG> und schließlich auf <STRONG>PIN-Nummer entsperren</STRONG>.

    
    </div>

6.  Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN festlegen**.

7.  Führen Sie im Dialogfeld **PIN festlegen** einen der folgenden Schritte aus:
    
      - Damit lync Server 2013 die PIN des Benutzers generieren kann, wählen Sie **automatisch eine gültige Pin generieren** (Standardeinstellung) aus.
    
      - Zum Erstellen einer eigenen PIN klicken Sie auf **Bestimmte PIN manuell eingeben**, klicken Sie auf das Textfeld, und geben Sie anschließend eine PIN ein, welche die in Ihren PIN-Richtlinieneinstellungen angegebenen PIN-Anforderungen erfüllt.

8.  Klicken Sie auf **OK**.

9.  Führen Sie im Abschnitt **PIN festlegen** eine der folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **PIN anzeigen**, um die PIN anzuzeigen, kopieren Sie die PIN, und teilen Sie sie dem Benutzer über die bevorzugte Methode Ihrer Organisation mit.
    
      - Klicken Sie auf **E-Mail-Anwendung zum Senden der neuen PIN an den Benutzer öffnen**, um die PIN per E-Mail zu senden. Wenn Sie Microsoft Office Outlook als E-Mail-Client verwenden, wird die PIN automatisch in die neue E-Mail-Nachricht kopiert. Wenn Sie einen anderen E-Mail-Client einsetzen, aktivieren Sie das Kontrollkästchen **PIN anzeigen**, und kopieren Sie die PIN anschließend in die E-Mail-Nachricht.

10. Klicken Sie auf **Schließen**.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Zuweisen einer Benutzer-PIN mithilfe von Windows PowerShell-Cmdlets

Sie können auch PIN-Nummern zuweisen, die mithilfe des Cmdlets "CsClientPin" zugewiesen werden können. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>So weisen Sie einem Benutzer automatisch eine PIN-Nummer zu

  - Der folgende Befehl weist dem Benutzer Ken Myer eine PIN zu. Da der PIN-Parameter nicht enthalten ist, generiert lync Server automatisch die PIN-Nummer und weist Sie zu.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>So weisen Sie einem Benutzer eine bestimmte PIN-Nummer zu

  - Der folgende Befehl verwendet den PIN-Parameter, um dem Benutzer Ken Myer die PIN 121989 zuzuweisen.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Zugriffsnummer für Einwahlkonferenz](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))  


[Konfigurieren von PIN-Regeln (private Identification Number) für Einwahlkonferenzen in lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

