---
title: Anzeigen von Benutzer-PIN-Informationen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Zusammenfassung: Anzeigen von Benutzer-PIN-Informationen in Skype for Business Server.'
ms.openlocfilehash: 236148de5b100220731d723df3217205b258879e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818687"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Anzeigen von Benutzer-PIN-Informationen in Skype for Business Server
 
**Zusammenfassung:** Anzeigen von Benutzer-PIN-Informationen in Skype for Business Server.
  
Um an einer Einwahlkonferenz als authentifizierter Benutzer teilzunehmen, erfordert ein Skype for Business Server-Benutzer mit den Anmeldeinformationen für Active Directory-Domänendienste (AD DS) eine persönliche Identifikationsnummer (PIN). Sie können die PIN-Informationen eines Benutzers über die Skype for Business Server-Systemsteuerung anzeigen.
  
> [!NOTE]
> Sie können Informationen zum Pin-Status anzeigen, beispielsweise, ob die PIN festgesetzt wurde oder wann die PIN zuletzt geändert wurde, aber Sie können die aktuelle PIN nicht sehen, indem Sie den PIN-Status betrachten. Wenn ein Benutzer seine PIN verloren hat, können Sie ihn zurücksetzen, indem Sie die Anweisungen unter [Festlegen der PIN für Einwahlkonferenzen eines Benutzers in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md) ausführen.
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>So zeigen Sie die PIN eines Benutzers in der Skype for Business Server-Systemsteuerung an

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
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
  
6. Klicken Sie auf einen Benutzer in den Suchergebnissen und dann auf **Aktion** und auf **PIN-Status anzeigen**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Benutzer-PIN-Informationen mithilfe von Windows PowerShell-Cmdlets

Sie können die PIN-Informationen für Benutzer mit dem Cmdlet „Get-CsClientPinInfo“ anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-view-user-pin-information"></a>So zeigen Sie die PIN-Informationen von Benutzern an

Um die PIN-Informationen für einen Benutzer anzuzeigen, geben Sie in der Skype for Business Server-Verwaltungsshell einen Befehl ähnlich dem folgenden ein, und drücken Sie dann die EINGABETASTE:
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Es werden etwa folgende Informationen zurückgegeben:

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .
  
## <a name="see-also"></a>Siehe auch

[Einrichten der PIN für Einwahlkonferenzen von Benutzern in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Sperren oder Entsperren einer Benutzer-PIN in Skype for Business Server](lock-or-unlock-a-user-pin.md)
