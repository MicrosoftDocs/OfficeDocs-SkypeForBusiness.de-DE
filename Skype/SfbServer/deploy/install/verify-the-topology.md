---
title: Überprüfen Sie die Topologie in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Zusammenfassung: Informationen zum Überprüfen der Skype für Business Server-Topologie und Active Directory-Server wie erwartet funktionieren. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 03dfb45c03aa104cc5a9b265a37c347380590877
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896421"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Überprüfen Sie die Topologie in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie die Skype für Business Server-Topologie überprüfen und Active Directory-Server wie erwartet funktionieren. Laden Sie eine kostenlose Testversion von Skype für Business Server aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Nachdem Sie die Topologie veröffentlicht und die Skype für Business Server Systemkomponenten auf jedem Server in der Topologie installiert haben, können Sie überprüfen, ob die Topologie wie erwartet funktioniert. Dazu gehören, die die Konfiguration aller Active Directory-Server weitergegeben wurde, damit die gesamte Domäne bekannt ist, dass Skype für Unternehmen verfügbar ist, in der Domäne überprüfen. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Überprüfen der Topologie wird in Schritt 8 des 8.
  
![Übersichtsdiagramm.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testen der Front-End-Poolbereitstellung

Der letzte Schritt besteht, testen den Front-End-Pool, und stellen Sie sicher, dass Skype für Business Clients miteinander kommunizieren kann. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Hinzufügen von Benutzern und Überprüfen der Clientkonnektivität

1. Verwenden Sie Active Directory-Computer und Benutzer hinzufügen, das Active Directory-Benutzerobjekt der Administratorrolle für die Skype für Business Server-Bereitstellung (auf dem Skype Business Server-Systemsteuerung installiert ist) der Gruppe **csadministrator hinzu** .
    
    > [!IMPORTANT]
    > Wenn Sie nicht die entsprechenden Benutzer und Gruppen zur Gruppe CsAdministors hinzufügen, wird eine Fehlermeldung beim Öffnen von Skype Business Server-Systemsteuerung die liest, "nicht autorisiert: Zugriff verweigert aufgrund einer rollenbasierten Zugriffssteuerung (RBAC) Autorisierungsfehler ." 
  
2. Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    
    > [!NOTE]
    > Das Benutzerkonto darf nicht den lokalen Administrator eines Servers mit Skype für Business Server sein. 
  
3. Verwenden Sie das Administratorkonto zur Anmeldung bei dem Computer, auf dem Skype Business Server-Systemsteuerung installiert ist.
    
4. Starten Sie Skype Business Server-Systemsteuerung, und klicken Sie dann die Anmeldeinformationen Sie, wenn Sie aufgefordert werden. Skype für Business Server-Systemsteuerung zeigt Informationen zur Bereitstellung.
    
5. In der linken Navigationsleiste auf **Topologie**, und stellen dann sicher, dass der Dienststatus auf einen Computer mit einem grünen Pfeil zeigt und für Replikationsstatus ein grünes Häkchen neben jedem Skype für Business Server-Rolle ist, die bereitgestellt und online geschaltet wurde. 
    
6. Klicken Sie in der linken Navigationsleiste auf **Benutzer** und dann auf **Benutzer aktivieren**. 
    
7. Klicken Sie auf der Seite **Neue Skype für Business Server-Benutzer** auf **Hinzufügen**.
    
8. Wenn Sie Suchparameter für die zu ermittelnden Objekte definieren möchten, aktivieren Sie auf der Seite **Aus Active Directory auswählen** die Option **Suchen** und klicken Sie optional auf **Filter hinzufügen**. Alternativ können Sie auch die Option **LDAP-Suche** aktivieren und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder einzuschränken. Klicken Sie auf **Suchen**, nachdem Sie die gewünschten Suchoptionen festgelegt haben.
    
9. Wählen Sie im Bereich mit den Suchergebnissen alle hinzuzufügenden Benutzer aus und klicken Sie dann auf **OK**.
    
10. Auf der Seite **Neue Skype für Business Server-Benutzer** sind in die Anzeige der **Benutzer** die Benutzer gewählte. In the **Assign users to a pool** list, select the server where the users should reside.
    
    Im Folgenden finden Sie eine Liste der Optionen, die Sie zum Konfigurieren der Objekte verwenden können.
    
    - **Generieren von SIP-URI des Benutzers**
    
    - **Telefonie**
    
    - **Anschluss-URI**
    
    - **Konferenzrichtlinie**
    
    - **Clientversionsrichtlinie**
    
    - **PIN-Richtlinie**
    
    - **Externe Zugriffsrichtlinie**
    
    - **Archivierungsrichtlinie**
    
    - **Standortrichtlinie**
    
    - **Clientrichtlinie**
    
    Um die grundlegenden Funktionen testen möchten, wählen Sie die Option, die Sie bevorzugen für die **SIP-URI des Benutzers generieren** -Einstellung (die anderen Optionen in der Standardeinstellungen Konfiguration verwenden), die und klicken Sie dann auf **Aktivieren**, wie in der Abbildung dargestellt.
    
     ![Aktivieren von Benutzern in der Systemsteuerung](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Es wird eine Zusammenfassungsseite angezeigt, auf der ein Häkchen in der Spalte **Aktiviert** darauf hinweist, dass die Benutzer eingerichtet sind. In der Spalte **SIP-Adresse** wird die Adresse angezeigt, die Sie zur Konfiguration der Benutzeranmeldung benötigen.
    
     ![Benutzer, die der Skype for Business Server-Systemsteuerung hinzugefügt wurden](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Melden Sie einen Benutzer bei einem Computer an, der mit der Domäne verknüpft ist, und einen weiteren Benutzer bei einem anderen Computer in der Domäne.
    
13. Installieren von Skype für Business-Client auf jedem den beiden Clientcomputern, und stellen Sie sicher, dass beide Benutzer sich zu Skype für Business Server anmelden können und Sofortnachrichten austauschen senden können.
    

