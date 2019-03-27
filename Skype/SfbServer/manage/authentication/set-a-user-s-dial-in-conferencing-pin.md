---
title: Einrichten eines Benutzers einwahlkonferenzen PIN in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Zusammenfassung: Festlegen des Benutzers einwahlkonferenzen PIN für Skype für Business Server.'
ms.openlocfilehash: 62b38b8ef15aa2283b66fc18abf5ec0e84e64870
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877391"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Einrichten eines Benutzers einwahlkonferenzen PIN in Skype für Business Server
 
**Zusammenfassung:** Ein Benutzer einwahlkonferenzen PIN für Skype für Business Server festgelegt.
  
Um eine Zugriffsnummer für Einwahl Konferenz als authentifizierter Benutzer teilzunehmen, erfordert einen Skype für Business Server-Benutzer mit Active Directory-Domänendienste (AD DS) Anmeldeinformationen eine persönliche Identifikationsnummer (PIN). Wenn ein Benutzer die Konferenz einwählen PIN vergisst oder die PIN nicht mithilfe von Skype für Business Server festgelegt, können Sie die Benutzer-PIN von Skype Business Server-Systemsteuerung festlegen. Die PIN kann entweder automatisch generiert oder manuell erstellt werden.
  
> [!NOTE]
> Bestimmte Eigenschaften der PIN, beispielsweise die Mindestlänge, können als Richtlinie konfiguriert werden. Zusätzlich zur globalen Richtlinie können Sie eine PIN-Richtlinie für einzelne Standorte oder Benutzer konfigurieren. 
  
### <a name="to-set-a-users-pin"></a>Festlegen der PIN eines Benutzers

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Benutzer**.
    
4. Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
   - Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.
    
   - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.
    
5. (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:
    
   a. Klicken Sie auf **Filter hinzufügen**.
    
   b. Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
   c. Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
   d. Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.
    
    > [!TIP]
    > Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben. 
  
   e. Klicken Sie auf **Suchen**.
    
    > [!NOTE]
    > Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf **Aktion** und auf **PIN entsperren**. 
  
6. Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN festlegen**.
    
7. Führen Sie im Dialogfeld **PIN festlegen** einen der folgenden Schritte aus:
    
   - Um Skype für Business Server zum Generieren der PIN des Benutzers zu ermöglichen, wählen Sie **Sie gültige PIN automatisch generieren** (Standardeinstellung).
    
   - Zum Erstellen einer eigenen PIN klicken Sie auf **Bestimmte PIN von Hand eingeben**, klicken Sie auf das Textfeld und geben Sie anschließend eine PIN ein, welche die in Ihren PIN-Richtlinieneinstellungen angegebenen PIN-Anforderungen erfüllt.
    
8. Klicken Sie anschließend auf **OK**.
    
9. Führen Sie im Abschnitt **PIN festlegen** eine der folgenden Aktionen aus: 
    
   - Aktivieren Sie das Kontrollkästchen **PIN anzeigen**, um die PIN anzuzeigen, kopieren Sie die PIN und teilen Sie sie dem Benutzer über die bevorzugte Methode Ihrer Organisation mit.
    
   - Klicken Sie auf **E-Mail-Client öffnen, um die neue PIN an den Benutzer zu senden**, um die PIN per E-Mail zu senden. Wenn Sie Microsoft Office Outlook als E-Mail-Client verwenden, wird die PIN automatisch in die neue E-Mail-Nachricht kopiert. Wenn Sie einen anderen E-Mail-Client einsetzen, aktivieren Sie das Kontrollkästchen **PIN anzeigen** und kopieren Sie die PIN anschließend in die E-Mail-Nachricht.
    
10. Klicken Sie auf **Schließen**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Zuweisen von PIN eines Benutzers mithilfe von Windows PowerShell-Cmdlets

Sie können Benutzern mithilfe des Cmdlets „Lock-Set-CsClientPin“ PINs zuweisen. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>So weisen Sie Benutzern automatisch PINs zu

Der folgende Befehl weist dem Benutzer Ken Myer eine PIN zu. Da der Pin-Parameter nicht angegeben ist, Skype für Business Server automatisch generiert und weisen Sie die PIN-Nummer.
    
  ```
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>So weisen Sie einem Benutzer eine bestimmte PIN zu

Der folgende Befehl verwendet den Parameter „Pin“, um dem Benutzer Ken Myer die PIN 121989 zuzuweisen.
    
  ```
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .
  

