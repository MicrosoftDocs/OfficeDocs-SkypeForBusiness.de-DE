---
title: 'Bereitstellen eines einheitlichen Kontaktspeichers in Skype for Business Server '
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Zusammenfassung: Aktivieren Sie den einheitlichen Kontaktspeicher in Skype for Business Server.'
---

# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Bereitstellen eines einheitlichen Kontaktspeichers in Skype for Business Server
 
**Zusammenfassung:** Aktivieren Sie den einheitlichen Kontaktspeicher in Skype for Business Server.
  
Zum Aktivieren des einheitlichen Kontaktspeichers in Skype for Business Server sind keine Topologieeinstellungen erforderlich. So aktivieren Sie den einheitlichen Kontaktspeicher für Benutzer:
  
- Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).
    
- Benutzer melden sich mindestens einmal mit Skype for Business an.
    
Nachdem die Kontakte eines Benutzers migriert wurden, was automatisch geschieht, wenn sich ein Benutzer bei Skype for Business anmeldet, kann der Benutzer auf seine Skype for Business Kontakte über Skype for Business, Outlook 2013 oder Outlook Web Access zugreifen und diese verwalten. Der Benutzer muss nicht bei Skype for Business angemeldet sein, um seine Kontakte über Outlook oder Outlook Web Access zu verwalten.
  
> [!IMPORTANT]
> Wenn sich ein Benutzer von Skype for Business nach der Migration anmeldet, sind Kontakte und Gruppen verfügbar und auf dem neuesten Stand, aber der Benutzer kann diese Kontakte nicht verwalten (d. h. hinzufügen, löschen, verschieben, markieren, aufheben oder ändern). 
  
## <a name="enable-users-for-unified-contact-store"></a>Aktivieren von Benutzern für den einheitlichen Kontaktspeicher

Wenn Sie Skype for Business Server bereitstellen und die Topologie veröffentlichen, ist der einheitliche Kontaktspeicher standardmäßig für alle Benutzer aktiviert. Sie müssen keine zusätzlichen Maßnahmen ergreifen, um den einheitlichen Kontaktspeicher zu aktivieren, nachdem Sie Skype for Business Server bereitgestellt haben. Sie können jedoch das Cmdlet **"Set-CsUserServicesPolicy** " verwenden, um anzupassen, welche Benutzer über einen einheitlichen Kontaktspeicher verfügen. Sie können dieses Feature global, nach Website, Nach Mandant oder nach Einzelpersonen oder Gruppen von Einzelpersonen aktivieren.
  
### <a name="to-enable-users-for-unified-contact-store"></a>So aktivieren Sie Benutzer für den einheitlichen Kontaktspeicher

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start**", auf **"Alle Programme**", auf **Skype for Business** und dann auf **Skype for Business Server Verwaltungsshell**.
    
2. Führen Sie einen der folgenden Schritte aus:
    
   - Um den einheitlichen Kontaktspeicher global für alle Skype for Business Server Benutzer zu aktivieren, verwenden Sie das folgende Cmdlet auf der Windows PowerShell Befehlszeilenschnittstelle:
    
   ```powershell
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Geben Sie an der Eingabeaufforderung Folgendes ein, um den einheitlichen Kontaktspeicher für die Benutzer an einer bestimmten Website zu aktivieren:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Beispiel:
    
   ```powershell
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Geben Sie an der Eingabeaufforderung Folgendes ein, um den einheitlichen Kontaktspeicher nach Mandant zu aktivieren:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Beispiel:
    
   ```powershell
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Geben Sie an der Eingabeaufforderung Folgendes ein, um den einheitlichen Kontaktspeicher für bestimmte Benutzer zu aktivieren:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > Sie können anstelle des Benutzeranzeigenamens auch einen Benutzeralias oder einen SIP-URI verwenden. 
  
    Beispiel:
    
   ```powershell
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > Im vorstehenden Beispiel wird mit dem ersten Befehl eine neue benutzerbezogene Richtlinie mit dem Namen UCS Enabled Users erstellt, für die das Flag „UcsAllowed“ auf „True“ festgelegt ist. Mit dem zweiten Befehl wird die Richtlinie dem Benutzer mit dem Anzeigename „Ken Myer“ zugewiesen, d. h., Ken Myer ist ab sofort für den einheitlichen Kontaktspeicher aktiviert.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrieren von Benutzern zum einheitlichen Kontaktspeicher

Die Kontakte eines Benutzers werden in den folgenden Fällen automatisch zum Exchange 2013-Server migriert:
  
- Dem Benutzer muss eine Benutzerdiensterichtlinie zugewiesen worden sein, für die die Option "UcsAllowed" auf "True" gesetzt ist.
    
- Wurde mit einem Exchange 2013-Postfach bereitgestellt und hat sich mindestens einmal beim Postfach angemeldet.
    
- Der Benutzer meldet sich mithilfe eines Skype for Business-Rich-Clients an.
    
Wenn sich der Benutzer mit einem Lync- oder einem früheren Client anmeldet oder der Benutzer nicht mit einem Exchange 2013-Server verbunden ist, wird die Benutzerdienstrichtlinie ignoriert, und die Kontakte des Benutzers verbleiben in Skype for Business Server.
  
Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden: 
  
- Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:
    
    \\ HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync<SIP-URL\>\UCS
    
    Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel den Wert InUCSMode mit dem Wert 2165.
    
- Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus. Geben Sie in der Befehlszeile der Skype for Business Server Verwaltungsshell Folgendes ein:
    
  ```powershell
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Ist **Test-CsUnifiedContactStore** erfolgreich, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.
    
## <a name="roll-back-migrated-users"></a>Zurücksetzen migrierter Benutzer

Wenn Sie das Feature für den einheitlichen Kontaktspeicher zurücksetzen müssen, führen Sie ein Rollback der Kontakte nur durch, wenn Sie den Benutzer zurück zu Exchange 2010 oder Lync Server 2010 verschieben. Deaktivieren Sie zum Zurücksetzen die Richtlinie für den Benutzer, und führen Sie dann das Cmdlet **Invoke-CsUcsRollback** aus. Das ausführen von **Invoke-CsUcsRollback** allein reicht nicht aus, um einen dauerhaften Rollback sicherzustellen, da die Migration des einheitlichen Kontaktspeichers erneut initiiert wird, wenn die Richtlinie nicht deaktiviert ist. Wenn beispielsweise ein Benutzer zurückgesetzt wird, weil Exchange 2013 auf Exchange 2010 zurückgesetzt wird und dann das Postfach des Benutzers in Exchange 2013 verschoben wird, wird die Migration des einheitlichen Kontaktspeichers sieben Tage nach dem Rollback erneut initiiert, solange der einheitliche Kontaktspeicher für den Benutzer in der Benutzerdienstrichtlinie weiterhin aktiviert ist.
  
Mit dem Cmdlet **"Move-CsUser**" wird der Kontaktspeicher des Benutzers in den folgenden Situationen automatisch von Exchange 2013 auf Skype for Business Server zurückgesetzt:
  
- Wenn Benutzer von Skype for Business Server zu Microsoft Lync Server 2013 oder Lync Server 2010 verschoben werden. 
    
- Wenn Benutzer standortübergreifend migriert werden, z. B. wenn ein Benutzer von Skype for Business Online zu Skype for Business Server lokal verschoben wird oder umgekehrt.
    
Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel:
  
- Wenn Sie Kontaktlisten exportieren, bevor die Kontakte der Benutzer zu Exchange 2013 migriert werden, und dann nach der Migration dieselben Daten importieren, sind die Daten des einheitlichen Kontaktspeichers und die Kontaktlisten beschädigt.
    
- Wenn Sie Benutzerdaten nach der Migration von Benutzern zu Exchange 2013 exportieren, ein Rollback der Migration ausführen und dann aus irgendeinem Grund die Daten nach der Migration importieren, sind die Daten des einheitlichen Kontaktspeichers und die Kontaktlisten beschädigt.
    
> [!IMPORTANT]
> Bevor Sie ein Exchange Postfach von Exchange 2013 auf Exchange 2010 verschieben, muss der Exchange Administrator sicherstellen, dass der Skype for Business Server Administrator das Skype for Business Server  Benutzerkontakte von Exchange 2013 bis Skype for Business Server. Informationen zum Zurücksetzen von Kontakten des einheitlichen Kontaktspeichers auf Skype for Business Server finden Sie weiter unten in diesem Abschnitt unter "So führen Sie ein Rollback der Kontakte des einheitlichen Kontaktspeichers von Exchange 2013 auf Skype for Business Server" durch. 
  
 **Zurücksetzen von Benutzerkontakten:** Wenn Sie das **Cmdlet "Move-CsUser**" verwenden, um Benutzer zwischen Skype for Business Server 2015 und Lync Server 2010 zu verschieben, können Sie diese Schritte überspringen, da das **Cmdlet "Move-CsUser**" automatisch einen Rollback des einheitlichen Kontaktspeichers ausführt, wenn Benutzer von Skype for Business Server 2015 zu Lync Server 2010 verschoben werden. **Move-CsUser** deaktiviert keine Richtlinie für den einheitlichen Kontaktspeicher, sodass die Migration zum einheitlichen Kontaktspeicher erneut erfolgt, wenn der Benutzer zurück zu Skype for Business Server 2015 verschoben wird.
  

