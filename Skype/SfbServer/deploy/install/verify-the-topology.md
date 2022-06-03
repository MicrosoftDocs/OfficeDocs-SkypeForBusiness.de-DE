---
title: Überprüfen der Topologie in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Zusammenfassung: Erfahren Sie, wie Sie überprüfen, ob die Skype for Business Server Topologie und Active Directory-Server wie erwartet funktionieren.'
ms.openlocfilehash: ec63977f4c70845f39aafe3521591ec93777f7d5
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860546"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Überprüfen der Topologie in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie überprüfen, ob die Skype for Business Server Topologie und Active Directory-Server wie erwartet funktionieren.
  
Nachdem Sie die Topologie veröffentlicht und die Skype for Business Server Systemkomponenten auf jedem der Server in der Topologie installiert haben, können Sie überprüfen, ob die Topologie wie erwartet funktioniert. Dazu gehört die Überprüfung, ob die Konfiguration an alle Active Directory-Server verteilt wurde, damit die gesamte Domäne weiß, Skype for Business in der Domäne verfügbar ist. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Überprüfen der Topologie ist Schritt 8 von 8.
  
![Übersichtsdiagramm.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testen der Bereitstellung des Front-End-Pools

Der letzte Schritt besteht darin, den Front-End-Pool zu testen und zu bestätigen, dass Skype for Business Clients miteinander kommunizieren können. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Hinzufügen von Benutzern und Überprüfen der Clientkonnektivität

1. Verwenden Sie Active Directory-Computer und -Benutzer, um das Active Directory-Benutzerobjekt der Administratorrolle für die Skype for Business Server Bereitstellung (auf der Skype for Business Server Systemsteuerung installiert ist) zur **CSAdministrator-Gruppe** hinzuzufügen.
    
    > [!IMPORTANT]
    > Wenn Sie der Gruppe "CsAdministors" nicht die entsprechenden Benutzer und Gruppen hinzufügen, wird beim Öffnen von Skype for Business Server Systemsteuerung die folgende Fehlermeldung angezeigt: "Nicht autorisiert: Zugriff aufgrund eines Autorisierungsfehlers der rollenbasierten Zugriffssteuerung (RBAC) verweigert". 
  
2. Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    
    > [!NOTE]
    > Das Benutzerkonto kann nicht der lokale Administrator eines Servers sein, auf dem Skype for Business Server ausgeführt wird. 
  
3. Melden Sie sich mit dem Administratorkonto bei dem Computer an, auf dem Skype for Business Server Systemsteuerung installiert ist.
    
4. Starten Sie Skype for Business Server Systemsteuerung, und geben Sie dann anmeldeinformationen an, wenn Sie dazu aufgefordert werden. Skype for Business Server Systemsteuerung zeigt Bereitstellungsinformationen an.
    
5. Klicken Sie in der linken Navigationsleiste auf **"Topologie**", und vergewissern Sie sich dann, dass der Dienststatus einen Computer mit einem grünen Pfeil anzeigt und dass sich neben jeder Skype for Business Server Rolle, die bereitgestellt und online gestellt wurde, ein grünes Häkchen für den Replikationsstatus befindet. 
    
6. Klicken Sie in der linken Navigationsleiste auf **"Benutzer**" und dann auf " **Benutzer aktivieren"**. 
    
7. Klicken Sie auf der Seite **"Neuer Skype for Business Server Benutzer**" auf **"Hinzufügen"**.
    
8. Um Suchparameter für die Objekte zu definieren, die Sie suchen möchten, können Sie auf der Seite **"Aus Active Directory auswählen** " die Option **"Suchen**" auswählen und dann optional auf **"Filter hinzufügen"** klicken. Sie können auch die **LDAP-Suche** auswählen und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder einzuschränken. Nachdem Sie sich für Ihre Suchoptionen entschieden haben, klicken Sie auf **"Suchen"**.
    
9. Wählen Sie im Bereich "Suchergebnisse" die Benutzer aus, die Sie hinzufügen möchten, und klicken Sie dann auf **"OK**".
    
10. Auf der Seite **"Neuer Skype for Business Server Benutzer**" werden die ausgewählten Benutzer **in der** Benutzeranzeige angezeigt. Wählen Sie in der Liste " **Benutzer einer Poolliste zuweisen** " den Server aus, auf dem sich die Benutzer befinden sollen.
    
    Im Folgenden finden Sie eine Liste der Optionen, die Sie zum Konfigurieren der Objekte verwenden können.
    
    - **Generieren des SIP-URI des Benutzers**
    
    - **Telefonie**
    
    - **Linien-URI**
    
    - **Konferenzrichtlinie**
    
    - **Clientversionsrichtlinie**
    
    - **PIN-Richtlinie**
    
    - **Richtlinie für den externen Zugriff**
    
    - **Archivierungsrichtlinie**
    
    - **Standortrichtlinie**
    
    - **Clientrichtlinie**
    
    Um die grundlegende Funktionalität zu testen, wählen Sie die Option aus, die Sie für die **SIP-URI-Einstellung des Benutzers generieren** bevorzugen (die anderen Optionen in der Konfiguration verwenden Standardeinstellungen), und klicken Sie dann auf **"Aktivieren"**, wie in der Abbildung dargestellt.
    
     ![Aktivieren Sie Benutzer in Systemsteuerung.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Es wird eine Zusammenfassungsseite angezeigt, auf der ein Häkchen in der Spalte **"Aktiviert** " angezeigt wird, um anzugeben, dass die Benutzer eingerichtet sind. In der **Spalte "SIP-Adresse** " wird die Adresse angezeigt, die Sie für die Benutzeranmeldungskonfiguration benötigen.
    
     ![Benutzer, die Skype for Business Server Systemsteuerung hinzugefügt wurden.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Melden Sie einen Benutzer bei einem Computer an, der mit der Domäne verbunden ist, und einen anderen Benutzer auf einem anderen Computer in der Domäne.
    
13. Installieren Sie Skype for Business Client auf jedem der beiden Clientcomputer, und stellen Sie dann sicher, dass sich beide Benutzer bei Skype for Business Server anmelden und Chatnachrichten aneinander senden können.
    

