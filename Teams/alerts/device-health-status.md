---
title: Microsoft Teams Geräteüberwachung und -warnung
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie die Teams Überwachungs- und Benachrichtigungsfunktionen im Microsoft Teams Admin Center verwenden, um den Integritätsstatus von Teams Geräten proaktiv zu überwachen.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: cca6be8274d26efe661a7a928ebb568aa054cfab2fb62206ee8f3649b37f4ea0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336196"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams Geräteintegritätsüberwachung

Die Geräteintegritätsüberwachung im Microsoft Teams Admin Center bietet Ihnen die Möglichkeit, die Integrität verschiedener Teams Geräte proaktiv zu überwachen. Überwachen Des Offlinestatus eines Geräts und Empfangen von Warnungen in Echtzeit, wenn das überwachte Gerät in Ihrer Organisation offline geht.  

Bevor Sie beginnen, benötigen Sie die Berechtigungen zum Erstellen von Teams/Kanälen in Ihrem Mandanten. [Weitere Informationen.](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)

## <a name="configure-device-state-rule"></a>Konfigurieren der Gerätestatusregel

1. Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers **Benachrichtigungen &**  >  **Warnungsregeln** aus.

   ![Abschnitt "Regeln" im Admin Center](../media/select-rules.png)

2. Wählen Sie auf der Seite **"Regeln"** die **Gerätestatusregel** aus.

3. Wählen Sie das Gerät aus, um die Statusregel zum Aktivieren von Warnungen zu konfigurieren.

    ![Teams Seite "Gerätestatusregel".](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretieren der Regelkonfiguration


|Feld |Beschreibung  |
|--------|-------------|
|**Regeltyp**   |Die Gerätestatusregel hilft Ihnen bei der effektiven Verwaltung. Teams Geräten und wird als Geräteverwaltungstyp klassifiziert. In Zukunft werden weitere Regeln des Geräteverwaltungstyps verfügbar sein, um andere verwandte Funktionen zu überwachen (Beispiele können sein: fehlerhaftes Gerät und der Anmeldestatus des Geräts).|
|**Bedingung**   |Sie können die Integrität von Geräten überwachen, wenn sie offline gehen. [Weitere Informationen](../devices/device-management.md) zur Geräteverwaltung finden Sie im Teams Admin Center. |
|**Scope**   |Sie können angeben, wie häufig der Gerätestatus überwacht werden soll, indem Sie die Regelauswertungshäufigkeit angeben. Standardmäßig werden Teams-Geräte nahezu in Echtzeit überwacht, wenn sie offline gehen. |
|**Gerätebenutzer**   |Sie können angeben, welche Geräte proaktive Offlineüberwachung benötigen, indem Sie sie basierend auf angemeldeten Benutzern auswählen. Weitere Informationen zur Konfiguration finden Sie unter ["Auswählen](#select-devices-for-configuration) von Geräten". |
|**Aktionen**  >  **Kanalwarnung**   |Im Abschnitt "Aktionen" können Sie Teams-Kanäle angeben, für die Sie Warnungen erhalten möchten. Derzeit wird ein Standardteam mit dem Namen **"Admin Alerts and Notifications" und** "Channel" mit dem Namen **"MonitoringAlerts"** erstellt, an das Benachrichtigungen übermittelt werden. <BR/> <BR/> Globale Administratoren und Teams Administratoren in Ihrem Mandanten werden diesem Standardteam automatisch hinzugefügt.|
|**Aktionen**  >  **Webhook**   |Sie können auch Benachrichtigungen mit einem externen Webhook abrufen (optional). Geben Sie eine externe öffentliche Webhook-URL im Webhook-Abschnitt an, an die eine JSON-Benachrichtigungsnutzlast gesendet wird. <BR/> <BR/>  Die Benachrichtigungsnutzlast kann über Webhooks in andere Systeme in Ihrer Organisation integriert werden, um benutzerdefinierte Workflows zu erstellen.<br/><br/> 

**JSON-Nutzlastschema für Webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **JSON-Beispielnutzlast:**<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Auswählen von Geräten für die Konfiguration

1. Sie können Teams Geräte auswählen, die Sie überwachen möchten, indem Sie Benutzer auswählen, die bei diesen Geräten angemeldet sind. Wählen Sie im Abschnitt **"Gerätebenutzer"** die Option **"Hinzufügen"** aus.

2. Wählen Sie einen oder mehrere Benutzer aus, für die Sie den Geräteintegritätsstatus überwachen möchten.

   ![Benutzer in Geräteintegritätsstatusregel hinzufügen.](../media/select-device-users.png )

   Die ausgewählte Liste der Benutzer wird im Abschnitt **"Gerätebenutzer"** angezeigt. Sie können diese Liste ändern, indem Sie Benutzer hinzufügen oder entfernen.

Alle Anmeldegeräte, die von der ausgewählten Liste der Benutzer verwendet werden, werden auf den Offlinestatus überwacht.

## <a name="notifications-in-teams-client"></a>Benachrichtigungen in Teams Client

Die Benachrichtigungen werden im automatisch erstellten **MonitoringAlerts-Kanal** des **Admin-Benachrichtigungs- und Benachrichtigungsteams** übermittelt.

Eine Offlinebenachrichtigung des Geräts kann die folgenden Informationen enthalten:

- Der Offline-Gerätename.
- Der Benutzer des Offlinegeräts.
- Gibt an, zu welcher Zeit das Gerät offline geschaltet wurde. (Derzeit wird die Uhrzeit in UTC angegeben.)
- Der Typ der Regel, die die Warnung ausgelöst hat.
- Warum eine Warnung ausgelöst wird.