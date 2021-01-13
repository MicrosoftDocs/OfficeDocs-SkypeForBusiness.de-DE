---
title: Konfigurieren von Richtlinien für das Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Richtlinienkonfiguration für Skype for Business Server 2015 Stress and Performance Tool.
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815035"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Konfigurieren von Richtlinien für das Skype for Business Server 2015 Stress and Performance Tool
 
Richtlinienkonfiguration für Skype for Business Server 2015 Stress and Performance Tool.
  
Es gibt mehrere Richtlinien und andere Bereiche, die Sie in Skype for Business Server 2015 konfigurieren können, bevor Sie das Stress and Performance Tool ausführen:
  
- [Archivierungsrichtlinie](configuring-policies.md#ArchivingPolicy)
    
- [Konferenzrichtlinie](configuring-policies.md#ConferencingPolicy)
    
- [Kontaktrichtlinie](configuring-policies.md#ContactsPolicy)
    
- [Verbundrichtlinie](configuring-policies.md#FederationPolicy)
    
- [Anrufsteuerungsrichtlinie](configuring-policies.md#CACPolicy)
    
- [Regeln für das Voicerouting](configuring-policies.md#VoiceRoutingRules)
    
- [Anwendung "Konferenz attendant"](configuring-policies.md#ConfAttendantApp)
    
- [Dienst zum Parken von Serveranrufen](configuring-policies.md#ServerCallParkServ)
    
- [Notrufe](configuring-policies.md#EmergencyCalls)
    
- [Konfigurieren der Reaktiongruppenanwendung](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Archivierungsrichtlinie
<a name="ArchivingPolicy"> </a>

Wenn Sie einen Archivierungsserver in Ihrer Skype for Business Server-Topologie bereitgestellt haben, können Sie das Skript ArchivingPolicy.ps1 sehen. Wenn Sie weitere Unterstützung benötigen, sehen Sie sich die Cmdlets für Archivierung und Webkonferenzen an.
  
## <a name="conferencing-policy"></a>Konferenzrichtlinie
<a name="ConferencingPolicy"> </a>

Für Konferenzen verfügen wir über das MeetingPolicy.ps1 Skript. Wenn Sie weitere Unterstützung benötigen, sehen Sie sich die Webkonferenz-Cmdlets an.
  
## <a name="contacts-policy"></a>Kontaktrichtlinie
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 Skript ist das Beispiel, das Sie überprüfen müssen. Die Cmdlets für Im- und Anwesenheitsangaben sind hilfreich, wenn Sie weitere Verweise benötigen.
  
## <a name="federation-policy"></a>Verbundrichtlinie
<a name="FederationPolicy"> </a>

Das Beispielskript für den Verbund ist FederationPolicy.ps1. Wenn Sie weitere Einblicke benötigen, sind Edgeserver, Verbund und externer Zugriff die zu überprüfende Cmdlets.
  
## <a name="call-admission-control-policy"></a>Anrufsteuerungsrichtlinie
<a name="CACPolicy"> </a>

Sie können auf BandwidthPolicy.ps1 für diese Richtlinie verweisen. Die Cmdlets für die Anrufsteuerung enthalten weitere Informationen.
  
## <a name="voice-routing-rules"></a>Regeln für das Voicerouting
<a name="VoiceRoutingRules"> </a>

Sie benötigen das RoutingRules.ps1 Beispielskript für das Voicerouting. Beachten Sie beim Konfigurieren dieser Regeln den Telefonkontext (d. h. /Location Profile oder /SimpleName) und interne/externe Ortscodes, damit Sie diese beim Erstellen von Benutzern angeben können. Sie benötigen sie auch während der LyncPerfTool-Konfiguration (speziell für PSTN-UC und UC-PSTN).
  
Beispielsweise sollte der Parameter "SimpleName" im Aufruf des Cmdlets **"New-CsDialPlan"** im Beispiel RoutingRules.ps1 für den Wert "LocationProfile" in der folgenden Abbildung der UserProfileGenerator.exe:
  
![Skype for Business-Ladekonfigurationstool, Registerkarte "Sprachszenarien", erweiterte Einstellungen für Unterhaltungen.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Weitere Informationen finden Sie in den Enterprise-VoIP Cmdlets.
  
## <a name="conference-attendant-application"></a>Anwendung "Konferenz attendant"
<a name="ConfAttendantApp"> </a>

Überprüfen Sie zuerst das ConferenceAutoAttendantConfiguration.ps1 Skript. Sie sollten die Telefonnummer "ConferencingAutoAttendant" (standardmäßig 1121111111) notieren, damit Sie sie wie folgt in das LyncPerfTool-Konfigurationstool für die Konfigurationsgenerierung eingeben können:
  
![Registerkarte "Sprachszenarien" mit Konferenzladeebene und Telefonnummer.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Weitere Informationen finden Sie in den Cmdlets für Konferenzen und Einwahlkonferenzen.
  
## <a name="server-call-park-service"></a>Dienst zum Parken von Serveranrufen
<a name="ServerCallParkServ"> </a>

Dies ist tatsächlich standardmäßig deaktiviert. Sie können das beispielskript CallParkConfiguration.ps1 überprüfen, wenn Sie dies testen müssen. Schauen Sie sich außerdem die Cmdlets für die Anwendung zum Parken von Anrufen nach Bedarf an.
  
## <a name="emergency-calls"></a>Notrufe
<a name="EmergencyCalls"> </a>

Sie müssen die folgenden Schritte ausführen, um Belastungs- und Leistungstests für Notrufe zu konfigurieren:
  
1. Richten Sie eine Sprachroute für Notrufe ein. Sie können das Skript RoutingRules.ps1 verwenden und unter dem Kommentar **"Route E911 to PSTN"** ein Beispiel für das Einrichten dieser Sprachroute suchen.
    
    > [!CAUTION]
    > Der Beispielbefehl in RoutingRules.ps1 hat ein Nummernmuster, das die Zahl 119 anstelle von 911 enthält. Vermeiden Sie die Verwendung von 911 (oder Ihrer tatsächlichen lokalen Notrufnummer), um versehentliche Anrufe an die lokalen Notrufoperatoren während der Auslastungstests zu verhindern. Denken Sie daran, dass diese Konfiguration nur zu Simulationszwecken dient! 
  
2. Konfigurieren Sie Adressen, indem Sie die Werte auf der Registerkarte "Konfiguration des **Standortinformationsdiensts"** im UserProvisioningTool angeben, wie in der folgenden Abbildung dargestellt:
    
     ![Benutzerbereitstellungstool mit der Anzahl der Adressen, Subnetze, Switches und Ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Wenn Sie alles in das UserProvisioningTool eingegeben haben, klicken Sie auf die Schaltfläche **"LIS-Konfigurationsdateien** generieren".
    
4. Nun werden CSV-Dateien für Ports, Subnetze, Switches und Funkzugriffspunkte (WaPs) sowie eine XML-Datei für das Stress and Performance-Tool generiert. Sie können die CSV-Dateien für Eingaben verwenden, wenn Sie den Standortinformationsdienst (Location Information Service, LIS) mit dem Skript LisConfiguration.ps1 konfigurieren. Dazu müssen Sie die Locations0.xml in denselben Ordner wie die ausführbare Datei des Stress and Performance Tools (LyncPerfTool.exe) verschieben. Dadurch können Sie Standortprofilszenarien (Wählplan) ausführen.
    
## <a name="configuring-response-group-application"></a>Konfigurieren der Reaktiongruppenanwendung
<a name="ConfigResponseGroupApp"> </a>

Das Beispielskript ist ResponseGroupConfiguration.ps1. Es gibt auch Cmdlets für Reaktionsgruppe-Anwendungen, die Sie auf weitere Konfigurationsdetails überprüfen können. Das folgende Diagramm zeigt einige der Konfigurationsdetails:
  
![Das Konfigurationstool für Reaktionsgruppe, das vorhandene Workflows zu Testzwecken zeigt.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

