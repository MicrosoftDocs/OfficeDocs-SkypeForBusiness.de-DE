---
title: Überlegungen zum Hinzufügen von Skype Room System-Domänen
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: In diesem Thema erfahren Sie, wie Sie einen Skype Room System-Appliance-PC zu Ihrer Domäne hinzufügen.
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093569"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Überlegungen zum Hinzufügen von Skype Room System-Domänen
 
In diesem Thema erfahren Sie, wie Sie einen Skype Room System-Appliance-PC zu Ihrer Domäne hinzufügen.
  
## <a name="domain-joining-considerations"></a>Überlegungen zur Domänenverknüpfung

Sie können den Skype Room System-Appliance-PC der Active Directory-Domäne hinzufügen oder ihn in einer Arbeitsgruppe be lassen. Berücksichtigen Sie die folgenden Punkte, bevor Sie diese Entscheidung treffen:
  
- Die Domänenverkettung des Skype Room System-Appliance-PCs hilft beim automatischen Importieren der privaten Stammzertifikatkette Ihrer Organisation.
    
- Durch die Domänenzuteilung am Skype Room System-Appliance-PC können Sie Domänenbenutzern und Gruppen Administratorrechte erteilen. Dadurch müssen Sie sich das Administratorkontokennwort auf lokaler Computerebene nicht merken.
    
- Wenn Sie einen Skype Room System-Appliance-PC mit der Domäne verbinden, müssen Sie eine separate Organisationseinheit (Organizational Unit, OU) erstellen, damit Sie Gruppenrichtlinienobjektausschlüsse für die Organisationseinheit bereitstellen können, in der sich alle Skype Room System-Computerobjekte befinden. Erstellen Sie dabei Computerobjekte in der Organisationseinheit, bevor Sie dem Skype Room System-Appliance-PC der Domäne beitreten.
    
- Viele Organisationen verfügen über die folgenden Gruppenrichtlinienobjekte, die sich auf die Funktionen des Skype Room System Appliance-PCs auswirken. Stellen Sie sicher, dass Sie die Vererbung dieser Gruppenrichtlinienobjekte in der Organisationseinheit Skype Room System außer Kraft setzen oder blockieren: 
    
  - Timeout der Anmeldesitzungen (automatische Sperrung)
    
  - Richtlinien für die Energieverwaltung
    
  - Erfordern zusätzlicher Authentifizierungsschritte
    
  - Verweigern des Zugriffs auf lokale Laufwerke
    
  - Benutzer zur Eingabe langsamer Netzwerkverbindungen aufforderen
    
  - Starten eines bestimmten Programms bei der Anmeldung
    
  - Erstellen Sie ein anderes Domänenbenutzerkonto auf allen Computern, die der Domäne beigetreten sind.
    
  - Push Windows Update to Skype Room System
    
- Alternativ können Sie den Appliance-PC in der Arbeitsgruppe be lassen. Wie beim Skype for Business-Desktopclient müssen Sie die Stammzertifikatkette manuell auf den Skype Room System-Appliance-PC importieren. Sie müssen die Stammzertifikatskette nicht importieren, wenn Ihre Skype for Business-Bereitstellung ein öffentliches Zertifikat verwendet (z. B. Vertraut, VeriSign und so weiter). 
    
Wenn Sie planen, Skype Room System-Computer mit der Domäne zu verbinden, um zu vermeiden, versehentlich zu einer unbeabsichtigten Organisationseinheit zu verbinden, die möglicherweise nicht frei von Gruppenrichtlinienobjekten ist, stellen Sie sicher, dass Sie der richtigen Organisationseinheit beitreten. Sie können das folgende Cmdlet auf dem Skype Room System-Computer verwenden, um an der richtigen Organisationseinheit teil zu nehmen und erhält keine Gruppenrichtlinienobjekte, die möglicherweise die Funktionalität von LRS blockieren. Wenden Sie sich an Ihren Systemadministrator oder OEM-Partner, um dieses Cmdlet ausführen zu können:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Auch wenn Sie eine separate Organisationseinheit erstellen und die Vererbung blockieren, gibt es einige Richtlinien, die probleme auf einer höheren Ebene verursachen könnten. Eine Gruppenrichtlinie ohne Überschreibung überschreibt eine Organisationseinheit mit der Einstellung Vererbung von Blockrichtlinien. Weitere Informationen finden Sie im Artikel [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in der Gruppenrichtliniendokumentation.
  
Möglicherweise haben Sie mehrere Ansätze, um diese Probleme zu lösen. Wir raten Ihnen, sich mit Ihren Active Directory-Experten zu beraten, um sicherzustellen, dass Ihnen eine Ou mit den entsprechenden Gruppenrichtlinieneinstellungen oder mindestens eine Organisationseinheit zur Verfügung gestellt wird, in der die zuvor beschriebenen Richtlinien nicht vorhanden sind. Es wird empfohlen, QoS (Quality of Service) für Skype Room System-Geräte zu aktivieren.

## <a name="see-also"></a>Siehe auch
  
[Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Verwalten der Dienstqualität](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)