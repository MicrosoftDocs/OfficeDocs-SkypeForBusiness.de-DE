---
title: 'Bereitstellen des einheitlichen Kontaktspeichers in Skype for Business Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1c9ebd8-af42-42a0-87d9-fc899fbd7c42
description: 'Zusammenfassung: Aktivieren des Unified Contact Stores in Skype for Business Server.'
ms.openlocfilehash: 737e9dbdd0dc9e4aae54e454cb558c59004719b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302803"
---
# <a name="deploy-unified-contact-store-in-skype-for-business-server"></a>Bereitstellen des einheitlichen Kontaktspeichers in Skype for Business Server
 
**Zusammenfassung:** Aktivieren Sie den einheitlichen Kontaktspeicher in Skype for Business Server.
  
Für die Aktivierung des Unified Contact Stores in Skype for Business Server sind keine topologieeinstellungen erforderlich. Zur Aktivierung des einheitlichen Kontaktspeichers für Benutzer müssen Sie die folgenden Punkte sicherstellen:
  
- Die Richtlinie für den einheitlichen Kontaktspeicher muss aktiviert sein (was in der Standardeinstellung der Fall ist).
    
- Benutzer melden sich mindestens einmal mit Skype for Business an.
    
Nachdem die Kontakte eines Benutzers migriert wurden, was automatisch geschieht, wenn sich ein Benutzer mit Skype for Business anmeldet, kann der Benutzer auf seine Skype for Business-Kontakte über Skype for Business, Outlook 2013 oder Outlook Web Access zugreifen und diese verwalten. Der Benutzer muss nicht bei Skype for Business angemeldet sein, um seine Kontakte aus Outlook oder Outlook Web Access zu verwalten.
  
> [!IMPORTANT]
> Wenn ein Benutzer sich nach der Migration von Skype for Business anmeldet, sind Kontakte und Gruppen verfügbar und auf dem neuesten Stand, aber der Benutzer kann diese Kontakte nicht verwalten (das heißt, Sie können diese Kontakte hinzufügen, löschen, verschieben, markieren, Markierung oder ändern). 
  
## <a name="enable-users-for-unified-contact-store"></a>Aktivieren von Benutzern für den einheitlichen Kontaktspeicher

Wenn Sie Skype for Business Server bereitstellen und die Topologie veröffentlichen, ist der Unified Contact Store standardmäßig für alle Benutzer aktiviert. Sie müssen keine weiteren Schritte Unternehmen, um den Unified Contact Store nach der Bereitstellung von Skype for Business Server zu aktivieren. Sie können jedoch das Cmdlet " **festlegen-CsUserServicesPolicy** " verwenden, um die verfügbaren Unified Contact Store-Benutzer anzupassen. Sie können dieses Feature Global, nach Website, nach Mandanten oder nach Einzelpersonen oder Gruppen von Personen aktivieren.
  
### <a name="to-enable-users-for-unified-contact-store"></a>So aktivieren Sie Benutzer für den einheitlichen Kontaktspeicher

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie einen der folgenden Schritte aus:
    
   - Wenn Sie den Unified Contact Store Global für alle Skype for Business Server-Benutzer aktivieren möchten, unter dem folgenden Cmdlet auf der Windows PowerShell-Befehlszeilenschnittstelle:
    
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

Die Kontakte eines Benutzers werden automatisch auf den Exchange 2013-Server migriert, wenn der Benutzer:
  
- Dem Benutzer muss eine Benutzerdienstrichtlinie zugewiesen worden sein, für die die Option „UcsAllowed“ auf „True“ gesetzt ist.
    
- Wurde mit einem Exchange 2013-Postfach bereitgestellt und hat sich mindestens einmal beim Postfach angemeldet.
    
- Melden Sie sich mit einem Rich-Client für Skype for Business an.
    
Wenn sich der Benutzer mit einem lync-oder früheren Client anmeldet oder wenn der Benutzer nicht mit einem Exchange 2013-Server verbunden ist, wird die Richtlinie für Benutzer Dienste ignoriert, und die Kontakte des Benutzers verbleiben in Skype for Business Server.
  
Verwenden Sie eine der folgenden Methoden, um zu ermitteln, ob die Kontakte eines Benutzers migriert wurden: 
  
- Überprüfen Sie den folgenden Registrierungsschlüssel auf dem Clientcomputer:
    
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\\<SIP URL\>\UCS
    
    Wenn die Kontakte des Benutzers in Exchange 2013 gespeichert sind, enthält dieser Schlüssel den Wert InUCSMode mit dem Wert 2165.
    
- Führen Sie das Cmdlet **Test-CsUnifiedContactStore** aus. Geben Sie in der Befehlszeile der Skype for Business Server-Verwaltungsshell Folgendes ein:
    
  ```
  Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
  ```

    Wenn**Test-CsUnifiedContactStore** erfolgreich ist, wurden die Kontakte des Benutzers zum einheitlichen Kontaktspeicher migriert.
    
## <a name="roll-back-migrated-users"></a>Zurücksetzen von migrierten Benutzern

Wenn Sie die Unified Contact Store-Funktion zurücksetzen müssen, setzen Sie die Kontakte nur zurück, wenn Sie den Benutzer wieder in Exchange 2010 oder lync Server 2010 zurück bewegen. Zum Zurücksetzen des Rollbacks deaktivieren Sie die Richtlinie für den Benutzer, und führen Sie dann das Cmdlet **Invoke-CsUcsRollback** aus. Nur die Ausführung von **Invoke-CsUcsRollback** allein reicht nicht aus, um einen dauerhaften Rollback zu gewährleisten, da die Migration von Unified Contact Store erneut initiiert wird, wenn die Richtlinie nicht deaktiviert ist. Wenn ein Benutzer beispielsweise zurückgesetzt wird, weil Exchange 2013 auf Exchange 2010 zurückgesetzt wird und dann das Postfach des Benutzers in Exchange 2013 verschoben wird, wird die Unified Contact Store-Migration sieben Tage nach dem Rollback erneut initiiert, solange der Unified Contact Store ist in der Richtlinie für Benutzer Dienste weiterhin für den Benutzer aktiviert.
  
Mit dem Cmdlet **Move-CsUser** wird in den folgenden Situationen automatisch der Kontaktspeicher des Benutzers von Exchange 2013 auf Skype for Business Server zurückgesetzt:
  
- Wenn Benutzer von Skype for Business Server zu Microsoft lync Server 2013 oder lync Server 2010 verschoben werden. 
    
- Wenn Benutzer über einen Standort migriert werden, beispielsweise wenn ein Benutzer von Skype for Business Online zu Skype for Business Server lokal oder umgekehrt verschoben wird.
    
Durch das Importieren der Daten eines einheitlichen Kontaktspeichers aus einer Sicherungsdatenbank können Daten des einheitlichen Kontaktspeichers und Benutzerdaten beschädigt werden, falls der einheitliche Kontaktspeichermodus zwischen dem Export und dem Import geändert wurde. Beispiel:
  
- Wenn Sie Kontaktlisten exportieren, bevor die Kontakte der Benutzer nach Exchange 2013 migriert werden, und dann nach der Migration dieselben Daten importieren, werden die Unified Contact Store-Daten und Kontaktlisten beschädigt.
    
- Wenn Sie Benutzerdaten exportieren, nachdem Sie Benutzer zu Exchange 2013 migriert haben, führen Sie die Migration zurück, und aus einem bestimmten Grund importieren Sie die Daten nach der Migration, und die Unified Contact Store-Daten und Kontaktlisten sind beschädigt.
    
> [!IMPORTANT]
> Bevor Sie ein Exchange-Postfach von Exchange 2013 auf Exchange 2010 verschieben, muss der Exchange-Administrator sicherstellen, dass der Skype for Business Server-Administrator zuerst die Skype for Business Server-Benutzer Kontakte von Exchange 2013 auf Skype für zurückgesetzt hat. Business Server. Informationen zum Rollback von Unified Contact Store-Kontakten in Skype for Business Server finden Sie unter Verfahren "So führen Sie einen Rollback für Unified Contact Store-Kontakte von Exchange 2013 zu Skype for Business Server" weiter unten in diesem Abschnitt durch. 
  
 **Wiederherstellen von Benutzerkontakten:** Wenn Sie das Cmdlet **Move-CsUser** verwenden, um Benutzer zwischen Skype for Business Server 2015 und lync Server 2010 zu verschieben, können Sie diese Schritte überspringen, da das Cmdlet **Move-CsUser** den Unified Contact Store automatisch zurücksetzt, wenn Nutzer von Skype für verschoben werden. Business Server 2015 auf lync Server 2010. **Verschieben-CsUser** deaktiviert die Unified Contact Store-Richtlinie nicht, sodass die Migration in den Unified Contact Store wiederholt wird, wenn der Benutzer zurück zu Skype for Business Server 2015 verschoben wird.
  

