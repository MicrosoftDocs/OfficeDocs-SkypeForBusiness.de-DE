---
title: Überprüfen der Topologie in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Zusammenfassung: Erfahren Sie, wie Sie überprüfen, ob die Skype for Business Server-Topologie und die Active Directory-Server wie erwartet funktionieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833835"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Überprüfen der Topologie in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie überprüfen, ob die Skype for Business Server-Topologie und die Active Directory-Server wie erwartet funktionieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center herunter.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Nachdem Sie die Topologie veröffentlicht und die Skype for Business Server-Systemkomponenten auf jedem Server in der Topologie installiert haben, können Sie überprüfen, ob die Topologie wie erwartet funktioniert. Dazu gehört die Überprüfung, ob die Konfiguration an alle Active Directory-Server verteilt wurde, damit die gesamte Domäne weiß, dass Skype for Business in der Domäne verfügbar ist. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Die Überprüfung der Topologie ist Schritt 8 von 8.
  
![Übersichtsdiagramm.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testen der Front-End-Poolbereitstellung

Der letzte Schritt besteht im Testen des Front-End-Pools und der Bestätigung, dass Skype for Business-Clients miteinander kommunizieren können. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Hinzufügen von Benutzern und Überprüfen der Clientkonnektivität

1. Verwenden Sie Active Directory-Computer und -Benutzer, um der Gruppe **"CSAdministrator"** das Active Directory-Benutzerobjekt der Administratorrolle für die Skype for Business Server-Bereitstellung (auf der die Skype for Business Server-Systemsteuerung installiert ist) hinzuzufügen.
    
    > [!IMPORTANT]
    > Wenn Sie der Gruppe "CsAdministors" nicht die entsprechenden Benutzer und Gruppen hinzufügen, wird beim Öffnen der Skype for Business Server-Systemsteuerung die Fehlermeldung "Nicht autorisiert: Der Zugriff wird aufgrund eines Autorisierungsfehlers bei der rollenbasierten Zugriffssteuerung verweigert" angezeigt. 
  
2. Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    
    > [!NOTE]
    > Das Benutzerkonto kann nicht der lokale Administrator eines Servers sein, auf dem Skype for Business Server ausgeführt wird. 
  
3. Melden Sie sich mit dem Administratorkonto am Computer an, auf dem die Skype for Business Server-Systemsteuerung installiert ist.
    
4. Starten Sie die Skype for Business Server-Systemsteuerung, und geben Sie die Anmeldeinformationen an, wenn Sie dazu aufgefordert werden. Die Skype for Business Server-Systemsteuerung zeigt Bereitstellungsinformationen an.
    
5. Klicken Sie in der linken Navigationsleiste auf **"Topologie",** und vergewissern Sie sich, dass der Dienststatus einen Computer mit einem grünen Pfeil zeigt und dass neben jeder Skype for Business Server-Rolle, die bereitgestellt und online geschaltet wurde, ein grünes Häkchen für den Replikationsstatus angezeigt wird. 
    
6. Klicken Sie in der linken Navigationsleiste **auf "Benutzer"** und dann **auf "Benutzer aktivieren".** 
    
7. Klicken Sie **auf der Seite "Neuer Skype for Business Server-Benutzer"** auf **"Hinzufügen".**
    
8. Zum Definieren von Suchparametern für die Objekte, die Sie suchen möchten, können Sie auf der Seite "Aus **Active Directory auswählen"** die Option "Suchen" auswählen und dann optional auf "Filter **hinzufügen" klicken.** Sie können auch die **LDAP-Suche auswählen** und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder zu begrenzen. Nachdem Sie sich für die Suchoptionen entschieden haben, klicken Sie auf **"Suchen".**
    
9. Wählen Sie im Bereich "Suchergebnisse" die Benutzer aus, die Sie hinzufügen möchten, und klicken Sie dann auf **"OK".**
    
10. Auf der **Seite "Neuer Skype for Business Server-Benutzer"** werden die ausgewählten Benutzer in der **Benutzeranzeige** angezeigt. Wählen Sie **in der Liste "Benutzer einer Poolliste** zuweisen" den Server aus, auf dem sich die Benutzer befinden sollen.
    
    Im Folgenden finden Sie eine Liste der Optionen, die Sie zum Konfigurieren der Objekte verwenden können.
    
    - **Generieren des SIP-URI des Benutzers**
    
    - **Telefonie**
    
    - **Zeilen-URI**
    
    - **Konferenzrichtlinie**
    
    - **Clientversionsrichtlinie**
    
    - **PIN-Richtlinie**
    
    - **Richtlinie für den externen Zugriff**
    
    - **Archivierungsrichtlinie**
    
    - **Standortrichtlinie**
    
    - **Clientrichtlinie**
    
    Um die grundlegende Funktionalität zu testen, wählen Sie die Option aus, die Sie für die **SIP-URI-Einstellung** des Benutzers generieren (die anderen Optionen in der Konfiguration verwenden Standardeinstellungen), und klicken Sie dann auf "Aktivieren", wie in der Abbildung dargestellt.
    
     ![Aktivieren Sie Benutzer in der Systemsteuerung.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Es wird eine Zusammenfassungsseite mit einem Häkchen in der Spalte **"Aktiviert"** angezeigt, das angibt, dass die Benutzer eingerichtet sind. In der Spalte "SIP-Adresse" wird die Adresse angezeigt, die Sie für die Benutzeranmeldekonfiguration benötigen. 
    
     ![Benutzer, die der Skype for Business Server-Systemsteuerung hinzugefügt wurden.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Melden Sie einen Benutzer an einem Computer an, der der Domäne beigetreten ist, und einen anderen Benutzer bei einem anderen Computer in der Domäne.
    
13. Installieren Sie den Skype for Business-Client auf jedem der beiden Clientcomputer, und stellen Sie dann sicher, dass sich beide Benutzer bei Skype for Business Server anmelden und Chatnachrichten miteinander senden können.
    

