---
title: Überwachung und Benachrichtigung von Microsoft Teams-Geräten
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
description: Erfahren Sie, wie Sie die Überwachungs- und Benachrichtigungsfunktionen von Teams im Microsoft Teams Admin Center verwenden, um den Integritätszustand von Teams-Geräten proaktiv zu überwachen.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 03a57da7af783fa95e0bccbcb6a96f183b2fbb90
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819463"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Überwachung des Gerätezustands von Microsoft Teams

Die Überwachung des Gerätezustands im Microsoft Teams Admin Center bietet Ihnen die Möglichkeit, die Integrität verschiedener Teams-Geräte proaktiv zu überwachen. Überwachen Sie den Offlinezustand eines Geräts, und erhalten Sie Benachrichtigungen in Echtzeit, wenn das überwachte Gerät in Ihrer Organisation offline geht.  

Bevor Sie beginnen, benötigen Sie die Berechtigungen zum Erstellen von Teams/Kanälen in Ihrem Mandanten. [Weitere Informationen](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>Konfigurieren der Gerätezustandsregel

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Center die Option **Benachrichtigungen & Regeln für Benachrichtigungen**  >  **aus.**

   ![Abschnitt "Regeln" im Admin Center](../media/select-rules.png)

2. Wählen Sie **auf der Seite** Regeln die Option **Gerätestatusregel aus.**

3. Wählen Sie das Gerät aus, um die Zustandsregel zum Aktivieren von Benachrichtigungen zu konfigurieren.

    ![Statusregelseite für Teams-Geräte.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretieren der Regelkonfiguration


|Feld |Beschreibung  |
|--------|-------------|
|**Regeltyp**   |Die Gerätezustandsregel hilft Ihnen bei der effektiven Verwaltung. Teams-Geräte und wird als Geräteverwaltungstyp klassifiziert. In Zukunft stehen weitere Regeln des Geräteverwaltungstyps zur Überwachung anderer verwandter Funktionen zur Verfügung (Beispiele hierfür sind: fehlerhaftes Gerät und der Anmeldestatus des Geräts).|
|**Bedingung**   |Sie können den Status von Geräten überwachen, wenn sie offline sind. [Weitere Informationen](https://docs.microsoft.com/microsoftteams/devices/device-management) zur Geräteverwaltung finden Sie im Teams Admin Center. |
|**Umfang**   |Sie können angeben, wie häufig Sie den Gerätestatus überwachen möchten, indem Sie die Häufigkeit der Regelauswertung erwähnen. Standardmäßig werden Teams-Geräte in nahezu Echtzeit überwacht, wenn sie offline sind. |
|**Gerätebenutzer**   |Sie können angeben, welche Geräte eine proaktive Offlineüberwachung benötigen, indem Sie sie basierend auf angemeldeten Benutzern auswählen. Weitere Informationen [finden Sie unter Auswählen](#select-devices-for-configuration) von Geräten für die Konfiguration. |
|**Aktionen**  >  **Kanalbenachrichtigung**   |Im Abschnitt Aktionen können Sie Teams-Kanäle angeben, für die Sie Benachrichtigungen erhalten möchten. Derzeit wird ein Standardteam mit dem Namen **Admin Alerts and Notifications** and channel namens **MonitoringAlerts** erstellt, an das Benachrichtigungen übermittelt werden. <BR/> <BR/> Globale Administratoren und Teams-Administratoren in Ihrem Mandanten werden diesem Standardteam automatisch hinzugefügt.|
|**Aktionen**  >  **Webhook**   |Sie können auch Benachrichtigungen mit einem externen Webhook erhalten (optional). Geben Sie eine externe öffentliche Webhook-URL im Webhook-Abschnitt an, in dem eine JSON-Benachrichtigungsnutzlast gesendet wird. <BR/> <BR/>  Die Benachrichtigungsnutzlast kann über Webhooks in andere Systeme in Ihrer Organisation integriert werden, um benutzerdefinierte Workflows zu erstellen.<br/><br/> 

**JSON-Nutzlastschema für Webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string "} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **Beispiel für JSON-Nutzlast:**<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": ":"Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Auswählen von Geräten für die Konfiguration

1. Sie können Teams-Geräte auswählen, die Sie überwachen möchten, indem Sie bei diesen Geräten angemeldete Benutzer auswählen. Wählen **Sie im** Abschnitt **Gerätebenutzer die** Option Hinzufügen aus.

2. Wählen Sie einen oder mehrere Benutzer aus, für die Sie den Gerätestatus überwachen möchten.

   ![Benutzer in der Statusregel für den Gerätestatus hinzufügen.](../media/select-device-users.png )

   Die ausgewählte Liste der Benutzer wird im **Abschnitt Gerätebenutzer** angezeigt. Sie können diese Liste ändern, indem Sie Benutzer hinzufügen oder entfernen.

Alle Anmeldegeräte, die von der ausgewählten Liste der Benutzer verwendet werden, werden auf den Offlinestatusstatus überwacht.

## <a name="notifications-in-teams-client"></a>Benachrichtigungen im Teams-Client

Die Benachrichtigungen werden im automatisch erstellten **MonitoringAlerts-Kanal** des **Admin Alerts and Notifications Teams** übermittelt.

Eine Geräte-Offlinebenachrichtigung kann die folgenden Informationen enthalten:

- Der Gerätename, der offline ist.
- Der Benutzer des Offlinegeräts.
- Die Uhrzeit, zu der das Gerät offline geschaltet wurde. (Derzeit wird die Uhrzeit in UTC angezeigt.)
- Der Typ der Regel, mit der die Warnung ausgelöst wurde.
- Warum eine Benachrichtigung ausgelöst wird
