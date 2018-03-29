---
title: Konfigurieren von Richtlinien für die Skype für Business Server 2015 Stress and Performance-Tool
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Richtlinienkonfiguration für Skype für Business Server 2015 Stress and Performance-Tool.
ms.openlocfilehash: 5bdeb4c65b3649e7d417550578e277e01e55fcc3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Konfigurieren von Richtlinien für die Skype für Business Server 2015 Stress and Performance-Tool
 
Richtlinienkonfiguration für Skype für Business Server 2015 Stress and Performance-Tool.
  
Es gibt mehrere Richtlinien und andere Bereiche, die Sie in Skype für Business Server 2015 konfigurieren können, vor dem Ausführen der Stress and Performance-Tool:
  
- [Archivierungsrichtlinie](configuring-policies.md#ArchivingPolicy)
    
- [Konferenzrichtlinie](configuring-policies.md#ConferencingPolicy)
    
- [Kontakte-Richtlinie](configuring-policies.md#ContactsPolicy)
    
- [Richtlinie für den Verbund](configuring-policies.md#FederationPolicy)
    
- [Call Admission Control-Richtlinie](configuring-policies.md#CACPolicy)
    
- [VoIP-Routing-Regeln](configuring-policies.md#VoiceRoutingRules)
    
- [Die Anwendung Konferenzzentrale Konferenz](configuring-policies.md#ConfAttendantApp)
    
- [Dienst zum Parken Server](configuring-policies.md#ServerCallParkServ)
    
- [Notrufe](configuring-policies.md#EmergencyCalls)
    
- [Konfigurieren der reaktionsgruppenanwendung](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Archivierungsrichtlinie
<a name="ArchivingPolicy"> </a>

Wenn Sie einen Archivierungsserver in Ihrer Skype für Business Server-Topologie bereitgestellt haben, können Sie das Skript ArchivingPolicy.ps1 anzeigen. Wenn Sie weitere Hilfe benötigen, checken Sie die Cmdlets für Archivierung und Webkonferenzen.
  
## <a name="conferencing-policy"></a>Konferenzrichtlinie
<a name="ConferencingPolicy"> </a>

Für Konferenzen haben wir das Skript MeetingPolicy.ps1. Wenn Sie weitere Hilfe benötigen, checken Sie die Cmdlets für Webkonferenzen.
  
## <a name="contacts-policy"></a>Kontakte-Richtlinie
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 Skript wird im Beispiel sein, die, das Sie benötigen, um zu prüfen. Die Cmdlets für Instant Messaging und Anwesenheit ist hilfreich, wenn Sie weitere Verweise benötigen.
  
## <a name="federation-policy"></a>Richtlinie für den Verbund
<a name="FederationPolicy"> </a>

Das Beispielskript für den Verbund ist FederationPolicy.ps1. Die Cmdlets zu überprüfen, wenn Sie weitere Erkenntnisse, benötigen, werden die Edge-Server, Partnerverbund und externer Zugriff.
  
## <a name="call-admission-control-policy"></a>Call Admission Control-Richtlinie
<a name="CACPolicy"> </a>

Sie können für diese Richtlinie auf BandwidthPolicy.ps1 verweisen. Call Admission Control-Cmdlets werden weitere Informationen sowie haben.
  
## <a name="voice-routing-rules"></a>VoIP-Routing-Regeln
<a name="VoiceRoutingRules"> </a>

Sie benötigen das RoutingRules.ps1 Beispielskript für VoIP-Routing. Wenn Sie diese Regeln konfigurieren, notieren Sie den Kontext (d. h., /Location Profil oder /SimpleName), Telefon und interner/externer Vorwahlen, damit Sie sie beim Erstellen von Benutzern angeben können. Sie benötigen auch während der Konfiguration (speziell für PSTN-UC und UC-zu-PSTN) LyncPerfTool eingetragenen.
  
Beispielsweise sollte der SimpleName-Parameter im Aufruf an das Cmdlet **New-CsDialPlan** im Beispiel RoutingRules.ps1 für den LocationProfile-Wert in der folgenden Abbildung der UserProfileGenerator.exe verwendet werden:
  
![Skype for Business-Lastkonfigurationstool, Registerkarte für VoIP-Szenarien, Erweiterte Einstellungen für Unterhaltungen](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Weitere Informationen hierzu können Sie die Enterprise-VoIP-Cmdlets überprüfen.
  
## <a name="conference-attendant-application"></a>Die Anwendung Konferenzzentrale Konferenz
<a name="ConfAttendantApp"> </a>

Überprüfen Sie zuerst das ConferenceAutoAttendantConfiguration.ps1 Skript. Sie sollten eine Notiz der Rufnummer ConferencingAutoAttendant (standardmäßig 1121111111), sodass Sie ihn in das Konfigurationstool für LyncPerfTool für Konfiguration Generation wie unten eingeben können:
  
![Die Registerkarte für VoIP-Szenarien zeigt die Stufe der Konferenzauslastung und die Telefonnummer.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Weitere Informationen finden Sie in den Konferenzen und Einwahlkonferenzen Cmdlets.
  
## <a name="server-call-park-service"></a>Dienst zum Parken Server
<a name="ServerCallParkServ"> </a>

Dies ist tatsächlich standardmäßig deaktiviert. Sie können das Beispielskript CallParkConfiguration.ps1 ansehen, wenn Sie benötigen, um dies zu testen. Darüber hinaus checken Sie die Cmdlets Call Park Anwendung wie gewünscht.
  
## <a name="emergency-calls"></a>Notrufe
<a name="EmergencyCalls"> </a>

Sie müssen die folgenden Schritte zum Konfigurieren von belastungs- und Leistungstests für Notrufe durchführen:
  
1. Richten Sie eine VoIP-Route für Notrufe. Sie können verwenden Sie das Skript RoutingRules.ps1 und prüfen Sie unter den Kommentar " **Route E911 mit PSTN** " für ein Beispiel dafür, wie diese VoIP-Route einrichten.
    
    > [!CAUTION]
    > Der Befehl im Beispiel in RoutingRules.ps1 hat ein Muster, die die Anzahl 119 statt 911 enthält. Sie sollten vermeiden der Verwendung von 911 (oder Ihre aktuelle lokale Notrufnummer), um versehentliche Anrufe an Ihre lokalen Notfällen Operatoren während die Auslastungstests zu verhindern. Beachten Sie, dass diese Konfiguration nur aus Gründen der Simulation ist! 
  
2. Konfigurieren Sie Adressen durch die Werte auf der Registerkarte **Info-Dienstkonfiguration Speicherort** in der UserProvisioningTool ausfüllen, wie in der folgenden Abbildung dargestellt:
    
     ![Das Benutzerbereitstellungstool zeigt die Anzahl der Adressen, Subnetze, Switche und Ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Wenn Sie alles in der UserProvisioningTool eingegeben haben, klicken Sie auf die Schaltfläche **LIS-Config-Dateien zu generieren** .
    
4. Nun wird CSV-Dateien für Ports, Subnetze, Switches und drahtlose Zugriffspunkte (drahtlose Zugriffspunkte) als auch eine XML-Datei für den Stress and Performance-Tool generiert. Die CSV-Dateien können für Eingaben beim Konfigurieren des Standortinformationen-Diensts (LIS) mit dem Skript LisConfiguration.ps1. Zu diesem Zweck müssen Sie die Datei Locations0.xml in demselben Ordner wie die Stress and Performance-Tool ausführbare (LyncPerfTool.exe) verschieben. Dadurch können Sie den Speicherort Profil (Wählplan) Szenarios auszuführen.
    
## <a name="configuring-response-group-application"></a>Konfigurieren der reaktionsgruppenanwendung
<a name="ConfigResponseGroupApp"> </a>

Das Beispielskript ist ResponseGroupConfiguration.ps1. Es gibt auch Cmdlets für die Reaktionsgruppenanwendung Weitere Einzelheiten zur Konfiguration überprüfen. Das folgende Diagramm zeigt einige der Konfigurationsdetails an:
  
![Das Konfigurationstool für Reaktionsgruppen zeigt vorhandene Workflows für Testzwecke.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

