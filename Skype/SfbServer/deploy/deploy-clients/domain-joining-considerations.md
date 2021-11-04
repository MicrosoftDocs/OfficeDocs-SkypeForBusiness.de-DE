---
title: Skype Überlegungen zur Verknüpfung von Raumsystemdomänen
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie einen Skype Room System-Anwendungs-PC mit Ihrer Domäne verknüpfen.
ms.openlocfilehash: a3a5e4b8fb1f4af7c67e0cfa91ff9237be438347
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751374"
---
# <a name="skype-room-system-domain-joining-considerations"></a>Skype Überlegungen zur Verknüpfung von Raumsystemdomänen
 
Lesen Sie dieses Thema, um zu erfahren, wie Sie einen Skype Room System-Anwendungs-PC mit Ihrer Domäne verknüpfen.
  
## <a name="domain-joining-considerations"></a>Überlegungen zur Domänenverknüpfung

Sie können den Skype Room System-Anwendungs-PC der Active Directory-Domäne hinzufügen oder in einer Arbeitsgruppe belassen. Berücksichtigen Sie die folgenden Punkte, bevor Sie diese Entscheidung treffen:
  
- Der Domänenbeitritt des Skype Room System-Anwendungs-PCs hilft beim automatischen Importieren der privaten Stammzertifikatkette Ihrer Organisation.
    
- Wenn Sie dem Skype Room System-Anwendungs-PC beitreten, können Sie Domänenbenutzern und Gruppen Administratorrechte erteilen. Dadurch müssen Sie sich das Kennwort für das Administratorkonto auf Computerebene nicht merken.
    
- Wenn Sie einen Skype Room System-Anwendungs-PC mit der Domäne verknüpfen, müssen Sie eine separate Organisationseinheit (Organizational Unit, OU) erstellen, damit Sie Gruppenrichtlinienobjektausschlüsse (Group Policy Object, GPO) für die OU bereitstellen können, in der sich alle Skype Room System-Computerobjekte befinden. Erstellen Sie in diesem Fall Computerobjekte in der OE, bevor Sie den Skype Room System-Anwendungs-PC mit der Domäne verknüpfen.
    
- Viele Organisationen verfügen über die folgenden GPOs, die sich auf Skype Room System-Appliance-PC-Funktionen auswirken. Stellen Sie sicher, dass Sie die Vererbung dieser GRUPPENrichtlinienobjekte in der Skype Room System OU außer Kraft setzen oder blockieren: 
    
  - Timeout von Anmeldesitzungen (automatische Sperre)
    
  - Richtlinien im Zusammenhang mit der Energieverwaltung
    
  - Zusätzliche Authentifizierungsschritte erforderlich
    
  - Verweigern des Zugriffs auf lokale Laufwerke
    
  - Auffordern von Benutzern zu langsamen Netzwerkverbindungen
    
  - Starten eines bestimmten Programms bei der Anmeldung
    
  - Erstellen Sie ein weiteres Domänenbenutzerkonto auf allen Computern, die einer Domäne beigetreten sind.
    
  - Push Windows Update auf Skype Room System
    
- Alternativ können Sie den Appliance-PC in der Arbeitsgruppe belassen. Wie beim Desktop-Skype for Business-Client müssen Sie dazu die Stammzertifikatkette manuell auf dem Skype Room System-Anwendungs-PC importieren. Sie müssen die Stammzertifikatskette nicht importieren, wenn Ihre Skype for Business Bereitstellung ein öffentliches Zertifikat verwendet (z. B. "Vereumer", "VeriSign" usw.). 
    
Wenn Sie beabsichtigen, Skype Raumsystemcomputer mit der Domäne zu verknüpfen, um zu vermeiden, dass Skype Raumsystemcomputer versehentlich mit einer unbeabsichtigten OU verknüpft wird, die möglicherweise nicht kostenlos von GPOs ist, stellen Sie sicher, dass Sie die richtige OU verknüpfen. Sie können das folgende Cmdlet aus dem Skype Raumsystemcomputer verwenden, um an der richtigen OU teilzunehmen, und sie erhalten keine GPOs, die möglicherweise die LRS-Funktionalität blockieren. Wenden Sie sich an Ihren Systemadministrator oder OEM-Partner, um das folgende Cmdlet auszuführen:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Selbst wenn Sie eine separate OU erstellen und die Vererbung blockieren, gibt es einige Richtlinien, die probleme auf einer höheren Ebene verursachen können. Eine Gruppenrichtlinie mit der Einstellung "Keine Außerkraftsetzung" schlägt eine OU mit einer Einstellung zum Blockieren der Richtlinienvererbung. Weitere Informationen finden Sie im Artikel ["Keine Außerkraftsetzung im Vergleich zur Blockierung der Richtlinienvererbung"](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in der Dokumentation zu Gruppenrichtlinien.
  
Möglicherweise haben Sie mehrere Ansätze, um diese Probleme zu lösen. Wir empfehlen Ihnen, sich an Ihre Active Directory-Experten zu wenden, um sicherzustellen, dass Ihnen eine ORGANISATIONSeinheit mit den entsprechenden GPO-Einstellungen oder mindestens eine OU zur Verfügung gestellt wird, in der die zuvor beschriebenen Richtlinien nicht vorhanden sind. Es wird empfohlen, Quality of Service (QoS) für Skype Raumsystemgeräte zu aktivieren.

## <a name="see-also"></a>Weitere Informationen
  
[Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Verwalten der Dienstqualität](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)