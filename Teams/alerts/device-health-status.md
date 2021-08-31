---
title: Microsoft Teams Geräteüberwachung und -benachrichtigung
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vapati
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Teams Überwachungs- und Benachrichtigungsfunktionen im Microsoft Teams Admin Center verwenden, um den Integritätszustand ihrer Teams proaktiv zu überwachen.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b44b564da4e772fb3e385b03d61be6874baf11c5
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58735352"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Microsoft Teams der Geräteinte health-Überwachung

Die Geräteintestüberwachung im Microsoft Teams Admin Center bietet Ihnen die Möglichkeit, den Status verschiedener Geräte proaktiv zu Teams überwachen. Überwachen Des Offlinestatus eines Geräts und Empfangen von Benachrichtigungen in Echtzeit, wenn das überwachte Gerät in Ihrer Organisation offline geschaltet wird.  

Bevor Sie beginnen, benötigen Sie die Berechtigungen zum Erstellen von Teams/Kanälen in Ihrem Mandanten. [Weitere Informationen.](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide)

## <a name="configure-device-state-rule"></a>Konfigurieren der Gerätestatusregel

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center die Option Benachrichtigungen **& Regeln für Benachrichtigungen**  >  **aus.**

   ![Abschnitt "Regeln" im Admin Center.](../media/select-rules.png)

2. Wählen Sie **auf der Seite** "Regeln" die Option **Gerätestatusregel aus.**

3. Wählen Sie das Gerät aus, um die Statusregel zum Aktivieren von Warnungen zu konfigurieren.

    ![Teams auf der Seite mit den Gerätestatusregel.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretieren der Regelkonfiguration


|Feld |Beschreibung  |
|--------|-------------|
|**Regeltyp**   |Die Gerätestatusregel hilft Ihnen bei der effektiven Verwaltung. Teams geräte und als Geräteverwaltungstyp klassifiziert. In Zukunft werden weitere Regeln für den Geräteverwaltungstyp zur Überwachung anderer zugehöriger Funktionen verfügbar sein (Beispiele hierfür sind fehlerhafte Geräte und der Anmeldestatus des Geräts).|
|**Bedingung**   |Sie können die Integrität von Geräten überwachen, wenn sie offline sind. [Weitere Informationen](../devices/device-management.md) zur Geräteverwaltung finden Sie im Teams Admin Center. |
|**Umfang**   |Sie können angeben, wie häufig der Gerätestatus überwacht werden soll, indem Sie die Häufigkeit der Regelauswertung erwähnen. Teams-Geräte werden standardmäßig in Echtzeit überwacht, wenn sie offline sind. |
|**Gerätebenutzer**   |Sie können angeben, welche Geräte eine proaktive Offlineüberwachung benötigen, indem Sie diese basierend auf angemeldeten Benutzern auswählen. Weitere Details [finden Sie unter Auswählen von](#select-devices-for-configuration) Geräten für die Konfiguration. |
|**Aktionen**  >  **Kanalwarnung**   |Im Abschnitt Aktionen können Sie Teams-Kanäle angeben, für die Sie Benachrichtigungen erhalten möchten. Derzeit wird ein Standardteam mit dem Namen **Administratorbenachrichtigungen** sowie Benachrichtigungen und Kanal mit dem Namen **MonitoringAlerts** erstellt, an das Benachrichtigungen übermittelt werden. <BR/> <BR/> Globale Administratoren und Teams in Ihrem Mandanten werden diesem Standardteam automatisch hinzugefügt.|
|**Aktionen**  >  **Webhook**   |Sie können Benachrichtigungen auch mit einem externen Webhook erhalten (optional). Geben Sie eine externe öffentliche Webhook-URL im Webhook-Abschnitt an, an die eine JSON-Benachrichtigungsnutzlast gesendet wird. <BR/> <BR/>  Die Benachrichtigungsnutzlast über Webhooks kann in andere Systeme in Ihrer Organisation integriert werden, um benutzerdefinierte Workflows zu erstellen.<br/><br/> 

**JSON-Nutzlastschema für Webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **JSON-Beispielnutzlast:**<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Geräte für die Konfiguration auswählen

1. Sie können die Teams, die Sie überwachen möchten, auswählen, indem Sie die Benutzer auswählen, die auf diesen Geräten angemeldet sind. Wählen **Sie im** Abschnitt **Gerätebenutzer die Option Hinzufügen** aus.

2. Wählen Sie einen oder mehrere Benutzer aus, für die Sie den Gerätestatus überwachen möchten.

   ![Benutzer zur Statusregel für den Gerätestatus hinzufügen.](../media/select-device-users.png )

   Die ausgewählte Benutzerliste wird im **Abschnitt Gerätebenutzer** angezeigt. Sie können diese Liste ändern, indem Sie Benutzer hinzufügen oder entfernen.

Alle von der ausgewählten Benutzerliste verwendeten Anmeldegeräte werden auf den Offlinestatus überwacht.

## <a name="notifications-in-teams-client"></a>Benachrichtigungen im Teams-Client

Die Benachrichtigungen werden im automatisch erstellten **MonitoringAlerts-Kanal** des **Admin Alerts and Notifications Teams** übermittelt.

Eine Geräte-Offlinebenachrichtigung kann die folgenden Informationen enthalten:

- Der Gerätename, der offline ist.
- Der Benutzer des Offlinegeräts.
- Wie lange ist das Gerät offline geschaltet? (Derzeit wird die Uhrzeit in UTC angezeigt.)
- Der Typ der Regel, die die Warnung ausgelöst hat.
- Warum eine Warnung ausgelöst wird