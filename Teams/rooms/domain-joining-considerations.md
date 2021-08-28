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
ms.localizationpriority: medium
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: Der Administrator kann erfahren, wie sie einen Skype-Gerät-PC (Room System) mit einer Active Directory-Domäne verbinden, zusammen mit den hierin zu berücksichtigenden Überlegungen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7956160f57971e48f1f979a7c0a905d760b767bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579599"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a>Überlegungen zur Domänenzusammenführung in Skype Room System
 
Lesen Sie dieses Thema und erfahren Sie, wie Sie Ihrer Domäne einen Skype Room System-Anwendungs-PC hinzufügen.
  
## <a name="domain-joining-considerations"></a>Überlegungen zur Domänenteilnahme

Sie können den PC Skype Raumsystemgerät mit der Active Directory-Domäne verbinden oder in einer Arbeitsgruppe be lassen. Berücksichtigen Sie die folgenden Punkte, bevor Sie diese Entscheidung treffen:
  
- Wenn Sie dem Skype Room System Appliance PC beitreten, können Sie die private Stammzertifikatkette Ihrer Organisation automatisch importieren.
- Wenn Sie dem Skype Room System Appliance PC beitreten, können Sie Domänenbenutzern und Gruppen Administratorrechte erteilen. Dadurch müssten Sie sich das Kennwort für das Administratorkonto auf Computerebene nicht merken.
- Wenn Sie der Domäne einen SKYPE Room System Appliance-PC hinzufügen, müssen Sie eine separate Organisationseinheit erstellen, damit Sie Gruppenrichtlinienobjektausschlüsse (Group Policy Object, GPO) für die Organisationseinheit bereitstellen können, in der sich alle Computerobjekte von Skype Room System befinden. Wenn Sie dies tun, erstellen Sie Computerobjekte in der Organisationseinheit, bevor Sie der Domäne den Skype Room System Appliance PC beitreten.
- Viele Organisationen verfügen über die folgenden Gruppenrichtlinienobjekte, die sich auf Skype Funktionen der Raumsystemgeräte-PC auswirken. Stellen Sie sicher, dass Sie die Vererbung dieser Gruppenrichtlinienobjekte in der Organisationseinheit Skype überschreiben oder blockieren:

  - Timeout von Anmeldesitzungen (automatische Sperre)
  - Richtlinien zur Energieverwaltung
  - Notwendigkeit zusätzlicher Authentifizierungsschritte
  - Verweigern des Zugriffs auf lokale Laufwerke
  - Benutzeraufforderungen bei langsamen Netzwerkverbindungen
  - Starten eines bestimmten Programms bei der Anmeldung
  - Erstellen eines weiteren Domänennutzerkontos auf allen Computern in der Domäne.
  - Push Windows Update auf Skype Raumsystem
    
- Alternativ könnten Sie sich dazu entschließen, den Anwendungs-PC in der Arbeitsgruppe zu belassen. Wie beim Desktopgerät Microsoft Teams oder Skype for Business müssen Sie dazu die Stammzertifikatkette manuell auf dem PC Skype Room System Appliance importieren. Sie müssen die Stammzertifikatkette nicht importieren, wenn ihre Bereitstellung ein öffentliches Zertifikat verwendet (z. B. "Anvertrauen", "VeriSign" und so weiter). 
    
Wenn Sie der Domäne Skype Raumsystem-Computer beitreten möchten, um zu vermeiden, dass Sie Skype Room System Machine versehentlich einer unbeabsichtigten Organisationseinheit beitreten, die möglicherweise nicht frei von Gruppenrichtlinienobjekten ist, stellen Sie sicher, dass Sie der richtigen Organisationseinheit beitreten. Sie können das folgende Cmdlet vom Computer Skype Raumsystem verwenden, um sich in der richtigen Organisationseinheit zu verbinden, und sie erhalten keine Gruppenrichtlinienobjekte, die möglicherweise die LRS-Funktionalität blockieren. Wenden Sie sich an Ihren Systemadministrator oder OEM-Partner, um diese Cmdlets ausführen zu lassen:
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

Selbst wenn Sie eine separate Organisationseinheit erstellen und die Vererbung blockieren, gibt es einige Richtlinien, die Probleme auf einer höheren Ebene verursachen könnten. Eine Gruppenrichtlinie mit „Nicht aufheben“-Einstellung hat Vorrang gegenüber einer OU mit „Richtlinienvererbung aufheben“-Einstellung. Weitere Informationen finden Sie [in](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) der Dokumentation zu Gruppenrichtlinien unter Keine Außerkraftsetzung im Vergleich zu "Richtlinienvererbung blockieren".
  
Unter Umständen stehen Ihnen mehrere Ansätze zur Lösung dieser Probleme zur Verfügung. Wir empfehlen Ihnen, sich an Ihre Active Directory-Experten zu wenden, um sicherzustellen, dass Sie über eine Organisationseinheit mit entsprechenden Gruppenrichtlinieneinstellungen oder mindestens eine Organisationseinheit, in der die zuvor beschriebenen Richtlinien nicht vorhanden sind, bereitgestellt werden. Es empfiehlt sich, Quality of Service (QoS) für Raumsystem Skype zu aktivieren.

## <a name="related-topics"></a>Verwandte Themen
  
[Gerätekonfiguration: Erstellen einer neuen oder Bearbeiten einer vorhandenen Gerätekonfiguration](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[Verwalten der Dienstqualität (Quality of Service, QoS)](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)