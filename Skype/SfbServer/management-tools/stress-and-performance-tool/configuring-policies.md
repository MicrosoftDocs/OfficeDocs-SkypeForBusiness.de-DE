---
title: Konfigurieren von Richtlinien für das Stress-und Leistungs Tool von Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Richtlinienkonfiguration für das Stress-und Leistungs Tool von Skype for Business Server 2015
ms.openlocfilehash: 5c8e4c296d06c736519a12da5b5e34c6f48e9ee2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299751"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Konfigurieren von Richtlinien für das Stress-und Leistungs Tool von Skype for Business Server 2015
 
Richtlinienkonfiguration für das Stress-und Leistungs Tool von Skype for Business Server 2015
  
Es gibt mehrere Richtlinien und andere Bereiche, die Sie in Skype for Business Server 2015 konfigurieren können, bevor Sie das Belastungs-und Leistungs Tool ausführen:
  
- [Archivierungsrichtlinie](configuring-policies.md#ArchivingPolicy)
    
- [Konferenzrichtlinie](configuring-policies.md#ConferencingPolicy)
    
- [Kontakt Richtlinie](configuring-policies.md#ContactsPolicy)
    
- [Föderations Richtlinie](configuring-policies.md#FederationPolicy)
    
- [Richtlinien für die Anrufsteuerung](configuring-policies.md#CACPolicy)
    
- [VoIP-Weiterleitungsregeln](configuring-policies.md#VoiceRoutingRules)
    
- [Anwendung für Konferenzteilnehmer](configuring-policies.md#ConfAttendantApp)
    
- [Server-Anruf Park Service](configuring-policies.md#ServerCallParkServ)
    
- [Notrufe](configuring-policies.md#EmergencyCalls)
    
- [Konfigurieren der Antwortgruppen Anwendung](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Archivierungsrichtlinie
<a name="ArchivingPolicy"> </a>

Wenn Sie einen Archivierungsserver in Ihrer Skype for Business Server-Topologie bereitgestellt haben, können Sie das ArchivingPolicy. ps1-Skript sehen. Wenn Sie weitere Hilfe benötigen, lesen Sie die Cmdlets Archivierungs-und Webkonferenz.
  
## <a name="conferencing-policy"></a>Konferenzrichtlinie
<a name="ConferencingPolicy"> </a>

Für Konferenzen haben wir das MeetingPolicy. ps1-Skript. Wenn Sie weitere Hilfe benötigen, lesen Sie die Webkonferenz-Cmdlets.
  
## <a name="contacts-policy"></a>Kontakt Richtlinie
<a name="ContactsPolicy"> </a>

Das ContactsPolicy. ps1-Skript ist das Beispiel, das Sie überprüfen müssen. Die Cmdlets für Sofortnachrichten und Anwesenheitsinformationen sind hilfreich, wenn Sie Weitere Verweise benötigen.
  
## <a name="federation-policy"></a>Föderations Richtlinie
<a name="FederationPolicy"> </a>

Das Beispielskript für Federation lautet FederationPolicy. ps1. Die zu überprüfenden Cmdlets, wenn Sie weitere Einblicke benötigen, sind Edgeserver, Federation und externer Zugriff.
  
## <a name="call-admission-control-policy"></a>Richtlinien für die Anrufsteuerung
<a name="CACPolicy"> </a>

Sie können auf BandwidthPolicy. ps1 für diese Richtlinie verweisen. Weitere Informationen finden Sie auch in den Cmdlets für die Anrufsteuerung.
  
## <a name="voice-routing-rules"></a>VoIP-Weiterleitungsregeln
<a name="VoiceRoutingRules"> </a>

Sie benötigen das RoutingRules. ps1-Beispielskript für das VoIP-Routing. Wenn Sie diese Regeln konfigurieren, notieren Sie sich den Telefonkontext (also/Location-Profil oder/SimpleName) sowie interne/externe Ortsvorwahl, damit Sie diese beim Erstellen von Benutzern angeben können. Sie benötigen Sie auch während der LyncPerfTool-Konfiguration (insbesondere für PSTN-UC und UC-PSTN).
  
Beispielsweise sollte der Parameter SimpleName im Aufruf des Cmdlets **New-CsDialPlan** im RoutingRules. ps1-Beispiel für den LocationProfile-Wert in der folgenden Abbildung von UserProfileGenerator. exe verwendet werden:
  
![Skype for Business-Lastkonfigurationstool, Registerkarte für VoIP-Szenarien, Erweiterte Einstellungen für Unterhaltungen](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Ausführliche Informationen finden Sie unter Enterprise-VoIP-Cmdlets.
  
## <a name="conference-attendant-application"></a>Anwendung für Konferenzteilnehmer
<a name="ConfAttendantApp"> </a>

Überprüfen Sie zuerst das ConferenceAutoAttendantConfiguration. ps1-Skript. Sie sollten die ConferencingAutoAttendant-Telefonnummer (standardmäßig 1121111111) notieren, damit Sie diese in das LyncPerfTool-Konfigurationstool für die Konfigurations Generierung eingeben können, wie unten beschrieben:
  
![Die Registerkarte für VoIP-Szenarien zeigt die Stufe der Konferenzauslastung und die Telefonnummer.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Weitere Details finden Sie unter Konferenz-und Einwahlkonferenz-Cmdlets.
  
## <a name="server-call-park-service"></a>Server-Anruf Park Service
<a name="ServerCallParkServ"> </a>

Dies ist standardmäßig deaktiviert. Sie können das CallParkConfiguration. ps1-Beispielskript überprüfen, wenn Sie dies testen möchten. Darüber hinaus können Sie die Cmdlets für die Parken-Anwendung nach Bedarf abrufen.
  
## <a name="emergency-calls"></a>Notrufe
<a name="EmergencyCalls"> </a>

Sie müssen die folgenden Schritte ausführen, um die Belastungs-und Leistungstests für Notrufe zu konfigurieren:
  
1. Einrichten einer VoIP-Route für Notrufe. Sie können das RoutingRules. ps1-Skript verwenden und unter dem Kommentar " **Route E911 to PSTN** " ein Beispiel für die Einrichtung dieser VoIP-Route finden.
    
    > [!CAUTION]
    > Der Beispielbefehl in RoutingRules. ps1 weist ein Zahlenmuster auf, das die Zahl 119 anstatt 911 enthält. Sie sollten die Verwendung von 911 (oder ihrer tatsächlichen lokalen Notfallnummer) vermeiden, um versehentliche Anrufe an Ihre lokalen Notfall Operatoren während der Auslastungstests zu verhindern. Beachten Sie, dass diese Konfiguration nur zu Simulationszwecken dient! 
  
2. Konfigurieren Sie Adressen, indem Sie die Werte auf der Registerkarte **Location Info Service config** im UserProvisioningTool ausfüllen, wie in der folgenden Abbildung dargestellt:
    
     ![Das Benutzerbereitstellungstool zeigt die Anzahl der Adressen, Subnetze, Switche und Ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Wenn Sie alles im UserProvisioningTool eingegeben haben, klicken Sie auf die Schaltfläche " **LIS-Konfigurationsdateien generieren** ".
    
4. Nun werden CSV-Dateien für Ports, Subnets, Switches und drahtlose Zugriffspunkte (WAPs) sowie eine XML-Datei für das Stress-und Leistungstool generiert. Sie können die CSV-Dateien für Eingaben verwenden, wenn Sie den Location Information Service (LIS) mit dem LisConfiguration. ps1-Skript konfigurieren. Zu diesem Zweck müssen Sie die Datei "Locations0. xml" in denselben Ordner wie die ausführbare Druck-und Leistungs Tool-Datei (LyncPerfTool. exe) verschieben. Auf diese Weise können Sie Standortprofil Szenarien (Wähl Plan) ausführen.
    
## <a name="configuring-response-group-application"></a>Konfigurieren der Antwortgruppen Anwendung
<a name="ConfigResponseGroupApp"> </a>

Das Beispielskript lautet ResponseGroupConfiguration. ps1. Es gibt auch Cmdlets für die Antwortgruppen Anwendung, die für weitere Konfigurationsdetails zu überprüfen sind. Im folgenden Diagramm werden einige Konfigurationsdetails angezeigt:
  
![Das Konfigurationstool für Reaktionsgruppen zeigt vorhandene Workflows für Testzwecke.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

