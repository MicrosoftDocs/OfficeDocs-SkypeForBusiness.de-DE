---
title: Überwachung und Benachrichtigung von Microsoft Teams-Geräten
author: cazawideh
ms.author: czawideh
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
description: Erfahren Sie, wie Sie die Überwachungs- und Benachrichtigungsfunktionen von Teams im Microsoft Teams Admin Center verwenden, um den Integritätsstatus von Teams-Geräten proaktiv zu überwachen.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 81994e3462fe678c40506d6a11b343ba733995cd
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67023806"
---
# <a name="microsoft-teams-device-health-monitoring"></a>Geräteintegritätsüberwachung in Microsoft Teams

Die Geräteintegritätsüberwachung im Microsoft Teams Admin Center bietet Ihnen die Möglichkeit, die Integrität verschiedener Teams-Geräte proaktiv zu überwachen. Überwachen Sie den Offlinestatus eines Geräts und empfangen Sie Benachrichtigungen in Echtzeit, wenn das überwachte Gerät in Ihrer Organisation offline geht.  

Bevor Sie beginnen, benötigen Sie die Teams/Kanalerstellungsberechtigungen in Ihrem Mandanten. [Weitere Informationen](/microsoft-365/solutions/manage-creation-of-groups?view=o365-worldwide).

## <a name="configure-device-state-rule"></a>Konfigurieren der Gerätestatusregel

1. Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers **die Option "Benachrichtigungen & Benachrichtigungsregeln** > " aus.

   ![Abschnitt "Regeln" im Admin Center.](../media/select-rules.png)

2. Wählen Sie auf der Seite **"Regeln** " die **Option "Gerätestatusregel"** aus.

3. Wählen Sie das Gerät aus, um die Statusregel zum Aktivieren von Warnungen zu konfigurieren.

    ![Statusregelseite für Teams-Geräte.](../media/device-state-rule.png )

## <a name="interpret-the-rule-configuration"></a>Interpretieren der Regelkonfiguration


|Feld |Beschreibung  |
|--------|-------------|
|**Regeltyp**   |Die Gerätezustandsregel hilft Ihnen bei der effektiven Verwaltung. Teams-Geräte und wird als Geräteverwaltungstyp klassifiziert. In Zukunft werden weitere Regeln des Geräteverwaltungstyps verfügbar sein, um andere verwandte Funktionen zu überwachen (Beispiele können folgende sein: fehlerhaftes Gerät und der Anmeldestatus des Geräts).|
|**Bedingung**   |Sie können die Integrität von Geräten überwachen, wenn sie offline gehen. [Erfahren Sie mehr](../devices/device-management.md) über die Geräteverwaltung im Teams Admin Center. |
|**Umfang**   |Sie können angeben, wie häufig der Geräteintegritätsstatus überwacht werden soll, indem Sie die Häufigkeit der Regelauswertung erwähnen. Standardmäßig werden Teams-Geräte nahezu in Echtzeit überwacht, wenn sie offline gehen. |
|**Gerätebenutzer**   |Sie können angeben, welche Geräte eine proaktive Offline-Statuenüberwachung benötigen, indem Sie sie basierend auf angemeldeten Benutzern auswählen. Weitere Informationen finden [Sie unter "Geräte auswählen" für die Konfiguration](#select-devices-for-configuration) . |
|**Aktionen** >  **Kanalbenachrichtigung**   |Im Abschnitt "Aktionen" können Sie Teams-Kanäle angeben, für die Sie Benachrichtigungen erhalten möchten. Derzeit wird ein Standardteam namens **Admin Warnungen und Benachrichtigungen** und kanal mit dem Namen **MonitoringAlerts** erstellt, an das Benachrichtigungen übermittelt werden. <BR/> <BR/> Globale Administratoren und Teams-Administratoren in Ihrem Mandanten werden diesem Standardteam automatisch hinzugefügt.|
|**Aktionen** >  **Webhook**   |Sie können auch Benachrichtigungen mit einem externen Webhook erhalten (optional). Geben Sie eine externe öffentliche Webhook-URL im Webhook-Abschnitt an, an die eine JSON-Benachrichtigungsnutzlast gesendet wird. <BR/> <BR/>  Die Benachrichtigungsnutzlast kann über Webhooks in andere Systeme in Ihrer Organisation integriert werden, um benutzerdefinierte Workflows zu erstellen.<br/><br/> 

**JSON-Nutzlastschema für Webhook:** <BR/><BR/>
<pre lang="json">{ <br/>    "type": "object",<br>    "properties": { <br/>      "AlertTitle": { "type": "string"} ,<br/>      "DeviceLoggedInUserId": { "type": "string" } ,<br/>      "DeviceId": { "type": "string" } , <br/>      "MetricValues": { <br/>            "type": "object",<br/>            "properties": { <br/>                 "DeviceHealthStatus": { "type": "string"} <br/>            } <br/>       } ,<br/>       "RuleName": { "type": "string"} ,<br/>       "RuleDescription": { "type": "string"} ,<br/>       "RuleFrequency": { "type": "string"} ,<br/>       "RuleType": { "type": "string"} ,<br/>       "TenantId": { "type": "string"} , <br/>       "RuleCondition": { "type": "string"} , <br/>       "AlertRaisedAt": { "type": "string"} <br/>    } <br/>} </pre> <br/> 

  **JSON-Beispielnutzlast**:<br/> <br/> <pre lang="JSON">    { <br/>      "AlertTitle":"*sample_device_name* of *User_Name* has become offline",<br/>      "DeviceLoggedInUserId": *User_GUID* ,<br/>      "DeviceId": *Device_GUID* , <br/>      "MetricValues": { <br/>         "DeviceHealthStatus": "offline" <br/>            }, <br/>        <br/>       "RuleName": "Device state rule" ,<br/>       "RuleDescription": "Alerts when device health status is detected as offline" ,<br/>       "RuleFrequency": "Real-time" ,<br/>       "RuleType": "Device Management" ,<br/>       "TenantId": *Tenant_GUID* , <br/>       "RuleCondition": "DeviceHealthStatus = Offline" , <br/>       "AlertRaisedAt": "2020-02-28T12:49:06Z" <br/>    }  </pre> <br/> 

## <a name="select-devices-for-configuration"></a>Auswählen von Geräten für die Konfiguration

1. Sie können Teams-Geräte auswählen, die Sie überwachen möchten, indem Sie bei diesen Geräten angemeldete Benutzer auswählen. Wählen Sie im Abschnitt **"Gerätebenutzer**" die Option **"Hinzufügen"** aus.

2. Wählen Sie einen oder mehrere Benutzer aus, für die Sie den Geräteintegritätsstatus überwachen möchten.

   ![Benutzer in geräteintegritätsstatusregel hinzufügen.](../media/select-device-users.png )

   Die ausgewählte Liste der Benutzer wird im Abschnitt **"Gerätebenutzer** " angezeigt. Sie können diese Liste ändern, indem Sie Benutzer hinzufügen oder entfernen.

Alle Anmeldegeräte, die von der ausgewählten Benutzerliste verwendet werden, werden auf den Offlinestatus überwacht.

## <a name="notifications-in-teams-client"></a>Benachrichtigungen im Teams-Client

Die Benachrichtigungen werden im automatisch erstellten **MonitoringAlerts-Kanal** des **Admin Benachrichtigungs- und Benachrichtigungsteam** übermittelt. Sie erhalten innerhalb von 15 Minuten nach dem Offlinebetrieb des Geräts eine Benachrichtigung. 

Eine Offlinebenachrichtigung eines Geräts kann die folgenden Informationen enthalten:

- Der Gerätename, der offline ist.
- Der Benutzer des Offlinegeräts.
- Zu welchem Zeitpunkt das Gerät offline geschaltet wurde. (Derzeit wird die Uhrzeit in UTC dargestellt.)
- Der Typ der Regel, die die Warnung ausgelöst hat.
- Warum eine Warnung ausgelöst wird.
