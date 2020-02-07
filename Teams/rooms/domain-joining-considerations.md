---
title: Überlegungen zur Domänenzusammenführung in Skype Room System
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie Ihrer Domäne einen Skype Room System-Anwendungs-PC hinzufügen.
ms.openlocfilehash: f2cad169b812d3da3a964c96adabc498df1009b8
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826083"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Überlegungen zur Domänenzusammenführung in Skype Room System
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie Ihrer Domäne einen Skype Room System-Anwendungs-PC hinzufügen.
  
## <a name="domain-joining-considerations"></a>Überlegungen zur Domänenteilnahme

Sie können den PC der Skype Room-System Einheit an die Active Directory-Domäne anschließen oder in einer Arbeitsgruppe belassen. Berücksichtigen Sie die folgenden Punkte, bevor Sie diese Entscheidung treffen:
  
- Domain-Beitritt zum Skype Room System Appliance PC hilft beim automatischen Importieren der privaten root-Zertifikatkette Ihres Unternehmens.
- Domain-Beitritt zum Skype Room System Appliance PC können Sie Domänenbenutzern und Gruppenadministrator Rechte erteilen. Dadurch müssten Sie sich das Kennwort für das Administratorkonto auf Computerebene nicht merken.
- Wenn Sie der Domäne einen Skype Room-systemappliance-PC beitreten, ist es erforderlich, dass Sie eine separate Organisationseinheit (Organizational Unit, OU) erstellen, damit Sie der Organisationseinheit, in der sich alle Skype Room-System Computerobjekte befinden, Gruppenrichtlinienobjekt-Ausschlüsse bereitstellen können. Wenn Sie dies tun, erstellen Sie in der Organisationseinheit Computerobjekte, bevor Sie dem PC der Skype Room-System Einheit zur Domäne beitreten.
- Viele Organisationen verfügen über die folgenden GPOs, die sich auf die PC-Funktionen der Skype Room-System Einheit auswirken. Stellen Sie sicher, dass Sie die Vererbung dieser GPOs in der Skype Room System ou außer Kraft setzen oder blockieren:

  - Timeout von Anmeldesitzungen (automatische Sperre)
  - Richtlinien in Bezug auf die Energieverwaltung
  - Notwendigkeit zusätzlicher Authentifizierungsschritte
  - Verweigern des Zugriffs auf lokale Laufwerke
  - Benutzeraufforderungen bei langsamen Netzwerkverbindungen
  - Starten eines bestimmten Programms bei der Anmeldung
  - Erstellen eines weiteren Domänennutzerkontos auf allen Computern in der Domäne.
  - Windows Update auf das Skype Room-System pushen
    
- Alternativ könnten Sie sich dazu entschließen, den Anwendungs-PC in der Arbeitsgruppe zu belassen. Wie bei den Desktop-Microsoft Teams oder dem Skype for Business-Client müssen Sie die Root-Zertifikatkette manuell auf dem PC der Skype Room-System Einheit importieren. Sie müssen die Stammzertifikatkette nicht importieren, wenn Ihre Bereitstellung ein öffentliches Zertifikat verwendet (beispielsweise Entrust, VeriSign usw.). 
    
Wenn Sie beabsichtigen, an der Domäne an Skype Room-System Computer teilzunehmen, um zu vermeiden, dass Sie versehentlich zu einer unbeabsichtigten ou, die nicht frei von GPOs ist, dem Skype Room-System Computer beitreten, stellen Sie bitte sicher, dass Sie der richtigen ou beitreten. Sie können das folgende Cmdlet vom Skype Room-System Computer verwenden, um an der richtigen Organisationseinheit teilzunehmen, und es werden keine GPOs empfangen, die die LRS-Funktionalität blockieren könnten. Wenden Sie sich an Ihren Systemadministrator oder OEM-Partner, wenn Sie Fragen zur Ausführung dieses Cmdlets haben:
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Sogar wenn Sie eine separate OU erstellen und die Vererbung blockieren, gibt es einige Richtlinien, die Probleme auf einer höheren Ebene verursachen könnten. Eine Gruppenrichtlinie mit „Nicht aufheben“-Einstellung hat Vorrang gegenüber einer OU mit „Richtlinienvererbung aufheben“-Einstellung. Weitere Informationen finden Sie im Artikel [keine Überschreibung im Vergleich zum Blockieren der Richtlinienvererbung](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in der Gruppenrichtliniendokumentation.
  
Unter Umständen stehen Ihnen mehrere Ansätze zur Lösung dieser Probleme zur Verfügung. Es wird empfohlen, dass Sie sich an Ihre Active Directory-Experten wenden, um sicherzustellen, dass Sie über eine OU mit den angemessenen GPO-Einstellungen oder wenigstens über eine OU verfügen, in der die weiter oben beschriebenen Richtlinien nicht vorhanden sind. Es wird empfohlen, Quality of Service (QoS) für Skype Room-System Geräte zu aktivieren.

## <a name="see-also"></a>Siehe auch
  
[Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Verwalten der Dienstqualität (Quality of Service, QoS)](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
