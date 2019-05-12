---
title: 'Bereitstellen des einheitlichen Kontaktspeicher in Skype für Business Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Zusammenfassung: Den einheitlichen Kontaktspeicher in Skype für Business Server zu aktivieren.'
ms.openlocfilehash: 725df8bf133e5b511e0004c161f9e661c5f9968d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894521"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Bereitstellen des einheitlichen Kontaktspeicher in Skype für Business Server
 
**Zusammenfassung:** Aktivieren Sie den einheitlichen Kontaktspeicher in Skype für Business Server.
  
Aktivieren des einheitlichen Kontaktspeicher in Skype für Business Server erfordert keine Einstellungen Topologie. Zur Aktivierung des einheitlichen Kontaktspeichers für Benutzer müssen Sie die folgenden Punkte sicherstellen:
  
- Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).
    
- Benutzer melden Sie sich mit Skype für Unternehmen mindestens einmal.
    
Nachdem die Kontakte eines Benutzers migriert wurden die automatisch geschieht, wenn ein Benutzer sich mit Skype für Unternehmen anmeldet, kann der Benutzer zugreifen und ihre Skype für Geschäftskontakte von Skype für Geschäftskunden, Outlook 2013 und Outlook Web Access verwalten. Der Benutzer hat keinen Skype für Unternehmen zum Verwalten ihrer Kontakte aus Outlook oder Outlook Web Access angemeldet sein.
  
> [!IMPORTANT]
> Wenn ein Benutzer von Skype für Unternehmen nach der Migration anmeldet, Kontakte und Gruppen verfügbar sind und auf dem neuesten Stand, aber der Benutzer ist nicht möglich (, die hinzugefügt wird, löschen, verschieben, markieren, Aufheben der Markierung von oder zu ändern,) verwalten die Kontakte. 
  
## <a name="enable-users-for-unified-contact-store"></a>Aktivieren von Benutzern für den einheitlichen Kontaktspeicher

Wenn Sie Skype für Business Server bereitstellen und veröffentlichen Sie die Topologie, ist einheitlichen Kontaktspeicher für alle Benutzer in der Standardeinstellung aktiviert. Sie müssen nicht keine weitere Aktion zum einheitlichen Kontaktspeicher nach der Bereitstellung von Skype für Business Server aktivieren. Das Cmdlet **"Set-csuserservicespolicy"** können Sie jedoch anpassen, welche Benutzer verfügbaren Kontaktspeicher unified haben. Sie können dieses Feature Global, von der Website, von Mandanten oder nach Personen oder Gruppen einzelner Benutzer aktivieren.
  
### <a name="to-enable-users-for-unified-contact-store"></a>So aktivieren Sie Benutzer für den einheitlichen Kontaktspeicher

1. Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Unternehmen**und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.
    
2. Führen Sie einen der folgenden Schritte aus:
    
   - Inter Sie zum einheitlichen Kontaktspeicher global für alle Skype für Business Server-Benutzer zu aktivieren, an der Windows PowerShell-Befehlszeilenschnittstelle das folgende Cmdlet aus:
    
   ```
   Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
   ```

   - Wenn Sie den einheitlichen Kontaktspeicher für die Benutzer an einem bestimmten Standort aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:
    
   ```
   New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
   ```

   Beispiel:
    
   ```
   New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
   ```

   - Wenn Sie den einheitlichen Kontaktspeicher nach Mandant aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:
    
   ```
   Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
   ```

   Beispiel:
    
   ```
   Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
   ```

   - Wenn Sie den einheitlichen Kontaktspeicher für bestimmte Benutzer aktivieren möchten, geben Sie an der Eingabeaufforderung Folgendes ein:
    
   ```
   New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
   ```

    > [!NOTE]
    > Sie können anstelle des Benutzeranzeigenamens auch einen Benutzeralias oder einen SIP-URI verwenden. 
  
    Beispiel:
    
   ```
   New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
   Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
   ```

    > [!NOTE]
    > Im vorstehenden Beispiel wird mit dem ersten Befehl eine neue benutzerbezogene Richtlinie mit dem Namen UCS Enabled Users erstellt, für die das Flag „UcsAllowed“ auf „True“ festgelegt ist. Mit dem zweiten Befehl wird die Richtlinie dem Benutzer mit dem Anzeigename „Ken Myer“ zugewiesen, d. h., Ken Myer ist ab sofort für den einheitlichen Kontaktspeicher aktiviert.
  
## <a name="migrate-users-to-unified-contact-store"></a>Migrieren von Benutzern zum einheitlichen Kontaktspeicher

Kontakte eines Benutzers werden automatisch auf den Exchange 2013-Server migriert, wenn der Benutzer:
  
- Dem Benutzer muss eine Benutzerdienstrichtlinie zugewiesen worden sein, für die die Option „UcsAllowed“ auf „True“ gesetzt ist.
    
- Mit einem Exchange 2013-Postfach bereitgestellt und mindestens einmal in das Postfach angemeldet hat.
    
- Protokolle in mithilfe einer Skype für Business-rich-Client.
    
Wenn der Benutzer sich mit einem Lync oder einem früheren Client anmeldet oder wenn der Benutzer nicht mit einem Exchange 2013-Server verbunden ist, der benutzerdiensterichtlinie ignoriert, und die Kontakte des Benutzers verbleiben in Skype für Business Server.
  
Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden: 
  
- Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS
    
    Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel einen Wert von InUCSMode mit einem Wert 2165.
    
- Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus. Geben Sie bei der Skype für Business Server-Verwaltungsshell Befehlszeile aus Folgendes ein:
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Wenn**Test-CsUnifiedContactStore** erfolgreich ist, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.
    
## <a name="roll-back-migrated-users"></a>Zurücksetzen von migrierten Benutzern

Wenn Sie einen Rollback müssen der Kontakt unified Feature speichern, Rollback für die Kontakte aus, nur, wenn Sie den Benutzer wieder zurück in Exchange 2010 oder Lync Server 2010 verschieben. Wenn Sie ein Rollback, deaktivieren Sie die Richtlinie für den Benutzer, und führen Sie das Cmdlet " **Invoke-CsUcsRollback** ". Nur ausführen **Invoke-CsUcsRollback** allein ist nicht genug sind, um permanente Rollback, stellen Sie sicher, da einheitlichen Kontaktspeicher Migration wird erneut gestartet werden, wenn die Richtlinie nicht deaktiviert ist. Beispielsweise wenn ein Benutzer rückgängig gemacht werden, da Exchange 2013 ein auf Exchange 2010 Rollback wird, und klicken Sie dann das Postfach des Benutzers in Exchange 2013 verschoben wird die einheitlichen Kontaktspeicher Migration erneut sieben Tage nach der Rollback initiiert werden, solange unified Contact speichern ist für den Benutzer in der Benutzerrichtlinie Services noch aktiviert.
  
Das Cmdlet **Move-CsUser** automatisch ein Rollback Kontaktspeicher des Benutzers von Exchange 2013 um Skype für Business Server in den folgenden Situationen:
  
- Wenn Benutzer von Skype für Business Server auf Microsoft Lync Server 2013 oder Lync Server 2010 verschoben werden. 
    
- Wenn Benutzer firewallübergreifenden vor Ort, beispielsweise wenn ein Benutzer von Skype für Business Online auf Skype für Business Server lokal, verschoben wird migriert werden oder umgekehrt.
    
Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel:
  
- Wenn Sie Kontaktlisten exportieren, bevor Kontakte des Benutzers in Exchange 2013 migriert werden und anschließend, nach der Migration die gleichen Daten importieren werden den einheitlichen Kontaktspeicher Daten und Kontaktlisten beschädigt.
    
- Wenn Sie nach dem Migrieren von Benutzern zu Exchange 2013 Benutzerdaten exportieren, Rollbacks der Migration und dann aus irgendeinem Grund, dass Sie nach der Migration die Daten importieren die unified Contact Daten zu speichern und Kontaktlisten beschädigt.
    
> [!IMPORTANT]
> Bevor Sie ein Exchange-Postfach von Exchange 2013 in Exchange 2010 verschieben, muss der Exchange-Administrator sicherstellen, dass die Skype für Business Server-Administrator zuerst die Skype für Business Server Benutzerkontakte von Exchange 2013 Skype für ein Rollback auf hat Business-Server. Zum einheitlichen Kontaktspeicher Kontakte Skype für Business Server wiederherstellen, finden Sie Verfahren "so Rollback für Kontakte des einheitlichen Kontaktspeicher von Exchange 2013 an Skype For Business Server" weiter unten in diesem Abschnitt. 
  
 **Wie Rollback für Benutzerkontakte:** Wenn Sie das Cmdlet **Move-CsUser** zum Verschieben von Benutzern zwischen Skype für Business Server 2015 und Lync Server 2010 verwenden, können Sie diese Schritte überspringen, da das **Move-CsUser** -Cmdlet automatisch einheitlichen Kontaktspeicher Rollback ausführt, wenn es von Skype für Benutzer wechselt Business Server 2015 zu Lync Server 2010. **Move-CsUser** wird nicht einheitlichen Kontaktspeicher-Richtlinie deaktiviert, damit die Migration zu einheitlichen Kontaktspeicher wiederholt werden soll, wenn der Benutzer wieder in Skype für Business Server 2015 verschoben wird.
  

