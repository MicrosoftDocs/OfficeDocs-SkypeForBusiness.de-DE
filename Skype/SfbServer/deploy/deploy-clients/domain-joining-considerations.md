---
title: Überlegungen zur Domänenzusammenführung in Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie Ihrer Domäne einen Skype Room System-Anwendungs-PC hinzufügen.
ms.openlocfilehash: e858122b8c931c53a7cb2eff0fe58ff225547a07
ms.sourcegitcommit: f76ac33ae47eafa2ae853cc031b6ac53c2d4fbbd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2018
---
# <a name="skype-room-system-domain-joining-considerations"></a>Überlegungen zur Domänenzusammenführung in Skype Room System
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie Ihrer Domäne einen Skype Room System-Anwendungs-PC hinzufügen.
  
## <a name="domain-joining-considerations"></a>Überlegungen zur Domänenteilnahme

Sie können die Appliance Skype Raum System PC zur Active Directory-Domäne beitreten zu oder verlassen es in einer Arbeitsgruppe. Berücksichtigen Sie die folgenden Punkte, bevor Sie diese Entscheidung treffen:
  
- Beitreten der Appliance Skype Raum System PC zu Domäne kann in Ihrer Organisation private stammzertifikatkette automatisch zu importieren.
    
- Beitreten der Appliance Skype Raum System PC zu Domäne können Sie Domänen-Benutzer und Gruppen über Administratorrechte erteilen. Dadurch müssten Sie sich das Kennwort für das Administratorkonto auf Computerebene nicht merken.
    
- Wenn Sie eine Einheit Skype Raum System PC mit der Domäne beitreten, ist es erforderlich, dass eine separate Organisationseinheit (OU), erstellen, sodass Sie Ausschlüsse Gruppenrichtlinienobjekt (GPO) für die Organisationseinheit vornehmen können, in denen alle Objekte der Skype Raum System Computer befinden. Wenn Sie dies tun, erstellen Sie vor der Teilnahme an der Appliance Skype Raum System PC auf die Domäne Computer-Objekte in der Organisationseinheit.
    
- Viele Unternehmen haben die folgenden Gruppenrichtlinienobjekte, die Skype Raum System Appliance PC-Funktionen auswirken. Stellen Sie sicher, dass Sie außer Kraft setzen oder die Vererbung von dieser Gruppenrichtlinienobjekte in der Organisationseinheit Skype Raum System blockieren: 
    
  - Timeout von Anmeldesitzungen (automatische Sperre)
    
  - Richtlinien in Bezug auf die Energieverwaltung
    
  - Notwendigkeit zusätzlicher Authentifizierungsschritte
    
  - Verweigern des Zugriffs auf lokale Laufwerke
    
  - Benutzeraufforderungen bei langsamen Netzwerkverbindungen
    
  - Starten eines bestimmten Programms bei der Anmeldung
    
  - Erstellen eines weiteren Domänennutzerkontos auf allen Computern in der Domäne.
    
  - Drücken Sie Windows Update, um Raum Skype-System
    
- Alternativ könnten Sie sich dazu entschließen, den Anwendungs-PC in der Arbeitsgruppe zu belassen. Als muss mit dem Desktop Skype, damit Business-Client, dies die stammzertifikatkette der Einheit Skype Raum System PC manuell importieren. Sie sind nicht erforderlich, um die stammzertifikatkette zu importieren, wenn Ihre Skype für die Business-Bereitstellung ein öffentliches Zertifikat (beispielsweise Entrust, VeriSign usw.) verwendet wird. 
    
Wenn Sie beabsichtigen, Skype Raum System Computern in der Domäne einbinden, um zu vermeiden, beitreten zu Skype Raum System Computer versehentlich zu einer unbeabsichtigten Organisationseinheit, die nicht frei von Gruppenrichtlinienobjekten sein können, stellen Sie sicher, dass Sie die richtige Organisationseinheit teilnehmen. Sie können das folgende Cmdlet vom Computer Skype Raum System verwenden, um in der richtigen Organisationseinheit teilnehmen und erhält keine Gruppenrichtlinienobjekte, die möglicherweise LRS Funktionen blockiert. Wenden Sie sich an Ihren Systemadministrator oder OEM-Partner, wenn Sie Fragen zur Ausführung dieses Cmdlets haben:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"

```

Sogar wenn Sie eine separate OU erstellen und die Vererbung blockieren, gibt es einige Richtlinien, die Probleme auf einer höheren Ebene verursachen könnten. Eine Gruppenrichtlinie mit „Nicht aufheben“-Einstellung hat Vorrang gegenüber einer OU mit „Richtlinienvererbung aufheben“-Einstellung. Weitere Informationen finden Sie im Artikel "No außer Kraft setzen As im Vergleich zu blockieren der Vererbung von Gruppenrichtlinien" in der Gruppenrichtlinien-Dokumentation unter http://technet.microsoft.com/en-us/library/cc978255.aspx.
  
Unter Umständen stehen Ihnen mehrere Ansätze zur Lösung dieser Probleme zur Verfügung. Es wird empfohlen, dass Sie sich an Ihre Active Directory-Experten wenden, um sicherzustellen, dass Sie über eine OU mit den angemessenen GPO-Einstellungen oder wenigstens über eine OU verfügen, in der die weiter oben beschriebenen Richtlinien nicht vorhanden sind. Es wird empfohlen, um Quality of Service (QoS) für Geräte Skype Raum System zu aktivieren.

## <a name="see-also"></a>Siehe auch

#### 
  
[Gerätekonfiguration: Erstellen Sie einer neuen oder bearbeiten Sie einer vorhandenen](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Verwalten von Quality of Service](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
