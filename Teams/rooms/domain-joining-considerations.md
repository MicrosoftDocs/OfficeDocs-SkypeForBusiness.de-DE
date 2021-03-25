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
description: Administratoren erfahren, wie Sie einem Skype Room System-Appliance-PC zu einer Active Directory-Domäne beitreten, zusammen mit den Überlegungen dazu.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117553"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Überlegungen zur Domänenzusammenführung in Skype Room System
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie Ihrer Domäne einen Skype Room System-Anwendungs-PC hinzufügen.
  
## <a name="domain-joining-considerations"></a>Überlegungen zur Domänenteilnahme

Sie können dem Skype Room System-Appliance-PC der Active Directory-Domäne beitreten oder ihn in einer Arbeitsgruppe beurlauben. Berücksichtigen Sie die folgenden Punkte, bevor Sie diese Entscheidung treffen:
  
- Die Domänenverkettung am Skype Room System-Appliance-PC hilft beim automatischen Importieren der privaten Stammzertifikatkette Ihrer Organisation.
- Mit der Teilnahme an der Domäne am Skype Room System-Appliance-PC können Sie Domänenbenutzern und Gruppen Administratorrechte gewähren. Dadurch müssten Sie sich das Kennwort für das Administratorkonto auf Computerebene nicht merken.
- Wenn Sie einem Skype Room System-Appliance-PC zur Domäne beitreten, müssen Sie eine separate Organisationseinheit (Ou) erstellen, damit Sie Gruppenrichtlinienobjektausschlüsse für die Organisationseinheit bereitstellen können, in der sich alle Skype Room System-Computerobjekte befinden. Erstellen Sie dabei Computerobjekte in der Organisationseinheit, bevor Sie dem Skype Room System-Appliance-PC der Domäne beitreten.
- Viele Organisationen verfügen über die folgenden Gruppenrichtlinienobjekte, die sich auf die PC-Funktionen der Skype Room System-Appliance auswirken. Stellen Sie sicher, dass Sie die Vererbung dieser Gruppenrichtlinienobjekte in der Organisationseinheit Skype Room System außer Kraft setzen oder blockieren:

  - Timeout von Anmeldesitzungen (automatische Sperre)
  - Richtlinien im Zusammenhang mit der Energieverwaltung
  - Notwendigkeit zusätzlicher Authentifizierungsschritte
  - Verweigern des Zugriffs auf lokale Laufwerke
  - Benutzeraufforderungen bei langsamen Netzwerkverbindungen
  - Starten eines bestimmten Programms bei der Anmeldung
  - Erstellen eines weiteren Domänennutzerkontos auf allen Computern in der Domäne.
  - Push Windows Update to Skype Room System
    
- Alternativ könnten Sie sich dazu entschließen, den Anwendungs-PC in der Arbeitsgruppe zu belassen. Wie beim Desktopclient von Microsoft Teams oder Skype for Business müssen Sie die Stammzertifikatkette auf dem Skype Room System-Appliance-PC manuell importieren. Sie müssen die Stammzertifikatkette nicht importieren, wenn Ihre Bereitstellung ein öffentliches Zertifikat verwendet (z. B. Anvertrauen, VeriSign und so weiter). 
    
Wenn Sie Skype Room System-Computer der Domäne beitreten möchten, um zu vermeiden, versehentlich zu einer unbeabsichtigten Organisationseinheit zu kommen, die möglicherweise nicht frei von Gruppenrichtlinienobjekten ist, stellen Sie sicher, dass Sie der richtigen Organisationseinheit beitreten. Sie können das folgende Cmdlet vom Skype Room System-Computer verwenden, um an der richtigen Organisationseinheit teil zu nehmen und empfangen keine Gruppenrichtlinienobjekte, die die Funktionalität von LRS blockieren könnten. Wenden Sie sich an Ihren Systemadministrator oder OEM-Partner, um die folgenden Cmdlets ausführen zu können:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Selbst wenn Sie eine separate Organisationseinheit erstellen und die Vererbung blockieren, gibt es einige Richtlinien, die probleme auf einer höheren Ebene verursachen könnten. Eine Gruppenrichtlinie mit „Nicht aufheben“-Einstellung hat Vorrang gegenüber einer OU mit „Richtlinienvererbung aufheben“-Einstellung. Weitere Informationen finden Sie unter [Keine Außerkraftsetzung im Vergleich zur Blockrichtlinienvererbung](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in der Dokumentation zu Gruppenrichtlinien.
  
Unter Umständen stehen Ihnen mehrere Ansätze zur Lösung dieser Probleme zur Verfügung. Wir empfehlen Ihnen, sich an Ihre Active Directory-Experten zu wenden, um sicherzustellen, dass Ihnen eine Organisationseinheit mit geeigneten Gruppenrichtlinieneinstellungen oder mindestens eine Organisationseinheit zur Verfügung gestellt wird, in der die zuvor beschriebenen Richtlinien nicht vorhanden sind. Wir empfehlen, QoS (Quality of Service) für Skype Room System-Geräte zu aktivieren.

## <a name="related-topics"></a>Verwandte Themen
  
[Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Verwalten der Dienstqualität (Quality of Service, QoS)](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)