---
title: Konfigurieren von Richtlinien für das Stress- und Leistungstool Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Richtlinienkonfiguration für Skype for Business Server 2015 Stress and Performance Tool.
ms.openlocfilehash: 3bf593402340386e21a2cc339b6eb971c7bbd39f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857322"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Konfigurieren von Richtlinien für das Stress- und Leistungstool Skype for Business Server 2015
 
Richtlinienkonfiguration für Skype for Business Server 2015 Stress and Performance Tool.
  
Es gibt mehrere Richtlinien und andere Bereiche, die Sie in Skype for Business Server 2015 konfigurieren können, bevor Sie das Stress and Performance Tool ausführen:
  
- [Archivierungsrichtlinie](configuring-policies.md#ArchivingPolicy)
    
- [Konferenzrichtlinie](configuring-policies.md#ConferencingPolicy)
    
- [Kontaktrichtlinie](configuring-policies.md#ContactsPolicy)
    
- [Verbundrichtlinie](configuring-policies.md#FederationPolicy)
    
- [Anrufsteuerungsrichtlinie](configuring-policies.md#CACPolicy)
    
- [VoIP-Routingregeln](configuring-policies.md#VoiceRoutingRules)
    
- [Konferenzzentralenanwendung](configuring-policies.md#ConfAttendantApp)
    
- [Dienst zum Parken von Serveranrufen](configuring-policies.md#ServerCallParkServ)
    
- [Notrufe](configuring-policies.md#EmergencyCalls)
    
- [Konfigurieren der Reaktionsgruppenanwendung](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Archivierungsrichtlinie
<a name="ArchivingPolicy"> </a>

Wenn Sie einen Archivierungsserver in Ihrer Skype for Business Server Topologie bereitgestellt haben, können Sie sich das Skript ArchivingPolicy.ps1 ansehen. Wenn Sie weitere Unterstützung benötigen, sehen Sie sich die Cmdlets für Archivierungs- und Webkonferenzen an.
  
## <a name="conferencing-policy"></a>Konferenzrichtlinie
<a name="ConferencingPolicy"> </a>

Für Konferenzen verfügen wir über das Skript MeetingPolicy.ps1. Wenn Sie weitere Unterstützung benötigen, sehen Sie sich die Webkonferenz-Cmdlets an.
  
## <a name="contacts-policy"></a>Kontaktrichtlinie
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 Skript wird das Beispiel sein, das Sie überprüfen müssen. Die Cmdlets für Chatnachrichten und Anwesenheitsinformationen sind hilfreich, wenn Sie weitere Verweise benötigen.
  
## <a name="federation-policy"></a>Verbundrichtlinie
<a name="FederationPolicy"> </a>

Das Beispielskript für den Partnerverbund ist FederationPolicy.ps1. Die zu überprüfenden Cmdlets, wenn Sie weitere Einblicke benötigen, sind Edgeserver, Partnerverbund und externer Zugriff.
  
## <a name="call-admission-control-policy"></a>Anrufsteuerungsrichtlinie
<a name="CACPolicy"> </a>

Sie können auf BandwidthPolicy.ps1 für diese Richtlinie verweisen. Die Cmdlets für die Anrufsteuerung verfügen auch über weitere Informationen.
  
## <a name="voice-routing-rules"></a>VoIP-Routingregeln
<a name="VoiceRoutingRules"> </a>

Sie benötigen das RoutingRules.ps1 Beispielskript für das VoIP-Routing. Wenn Sie diese Regeln konfigurieren, notieren Sie sich den Telefonkontext (d. h. /Location Profile oder /SimpleName) und die Codes für interne/externe Bereiche, damit Sie sie beim Erstellen von Benutzern angeben können. Sie benötigen sie auch während der LyncPerfTool-Konfiguration (speziell für PSTN-UC und UC-PSTN).
  
For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:
  
![Skype for Business Ladekonfigurationstool, Registerkarte "VoIP-Szenarien", "Erweiterte Einstellungen für Unterhaltungen".](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Ausführliche Informationen finden Sie in den Enterprise-VoIP Cmdlets.
  
## <a name="conference-attendant-application"></a>Konferenzzentralenanwendung
<a name="ConfAttendantApp"> </a>

Überprüfen Sie zunächst das skript ConferenceAutoAttendantConfiguration.ps1. Sie sollten die Telefonnummer "ConferencingAutoAttendant" (standardmäßig 1121111111) notieren, damit Sie sie wie folgt in das LyncPerfTool-Konfigurationstool für die Konfigurationsgenerierung eingeben können:
  
![Die Registerkarte "VoIP-Szenarien" mit konferenzbasierter Ladestufe und Telefonnummer.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Weitere Details finden Sie in den Cmdlets für Konferenzen und Einwahlkonferenzen.
  
## <a name="server-call-park-service"></a>Dienst zum Parken von Serveranrufen
<a name="ServerCallParkServ"> </a>

Dies ist standardmäßig deaktiviert. Sie können das CallParkConfiguration.ps1 Beispielskript überprüfen, wenn Sie dies testen müssen. Sehen Sie sich außerdem die Cmdlets für die Anwendung zum Parken von Anrufen nach Bedarf an.
  
## <a name="emergency-calls"></a>Notrufe
<a name="EmergencyCalls"> </a>

Sie müssen die folgenden Schritte ausführen, um Stress- und Leistungstests für Notrufe zu konfigurieren:
  
1. Richten Sie eine VoIP-Route für Notrufe ein. Sie können das skript RoutingRules.ps1 verwenden und unter dem Kommentar " **Route E911 to PSTN** " ein Beispiel für die Einrichtung dieser VoIP-Route überprüfen.
    
    > [!CAUTION]
    > Der Beispielbefehl in RoutingRules.ps1 weist ein Zahlenmuster auf, das die Zahl 119 anstelle von 911 enthält. Sie sollten die Verwendung von 911 (oder Ihrer tatsächlichen lokalen Notrufnummer) vermeiden, um versehentliche Anrufe an Ihre lokalen Notfalloperatoren während der Auslastungstests zu verhindern. Denken Sie daran, dass diese Konfiguration nur zu Simulationszwecken dient! 
  
2. Konfigurieren Sie Adressen, indem Sie die Werte auf der Registerkarte **"Location Info Service Config"** im UserProvisioningTool eingeben, wie in der folgenden Abbildung dargestellt:
    
     ![Benutzerbereitstellungstool mit der Anzahl der Adressen, Subnetze, Switches und Ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Wenn Sie alles in das UserProvisioningTool eingegeben haben, klicken Sie auf die Schaltfläche **"LIS-Konfigurationsdateien generieren".**
    
4. Jetzt werden CSV-Dateien für Ports, Subnetze, Switches und WAPs (Wireless Access Points) sowie eine XML-Datei für das Stress and Performance-Tool generiert. Sie können die CSV-Dateien für Eingaben verwenden, wenn Sie den Standortinformationsdienst (LOCATION Information Service, LIS) mit dem Skript LisConfiguration.ps1 konfigurieren. Dazu müssen Sie die Locations0.xml-Datei in denselben Ordner wie die ausführbare Datei des Stress and Performance Tools (LyncPerfTool.exe) verschieben. Auf diese Weise können Sie Standortprofilszenarien (Wählplanszenarien) ausführen.
    
## <a name="configuring-response-group-application"></a>Konfigurieren der Reaktionsgruppenanwendung
<a name="ConfigResponseGroupApp"> </a>

Das Beispielskript ist ResponseGroupConfiguration.ps1. Es gibt auch Cmdlets für Reaktionsgruppenanwendungen, um weitere Konfigurationsdetails zu überprüfen. Das folgende Diagramm zeigt einige der Konfigurationsdetails:
  
![Das Konfigurationstool für Reaktionsgruppen mit vorhandenen Workflows für Tests.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

