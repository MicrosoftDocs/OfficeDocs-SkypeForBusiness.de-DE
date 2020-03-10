---
title: Datensammlungsverfahren
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
hideEdit: true
description: Microsoft sammelt Zensus-, Nutzungs-und Fehlerdaten, um zu verstehen, wie Skype for Business verwendet wird und wo Benutzer Probleme auftreten. The data is used to plan product improvements.
ms.openlocfilehash: 1c88086038c3874ae95f6151c1d04d13e0b9ccaf
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583102"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Datensammlungsverfahren im Zusammenhang mit Skype for Business und Microsoft Teams

Skype for Business Server und Skype for Business Online, zusammen mit Skype for Business-und Microsoft Teams-apps, sammeln Daten, damit Microsoft verstehen kann, wie diese Produkte verwendet werden, und welche Arten von Fehlern, wie etwa Anmeldefehlern, aufgetreten sind. Anhand dieser Informationen können wir Nutzungsmuster verstehen, neue Funktionen planen, eine Problembehandlung durchführen und Problembereiche korrigieren.

Einige Nutzungsdaten werden automatisch gesammelt, andere Daten können hingegen nur gesammelt werden, wenn der Administrator und/oder Nutzer dies zulässt. Die Datensammlung unterteilt sich in diese drei Kategorien:

- Statistische Daten zum Nutzer

- Nutzungsdaten

- Fehlerberichtsdaten

## <a name="census-data"></a>Statistische Daten zum Nutzer

Census-Daten werden ausschließlich zur Bereitstellung, Unterstützung und Verbesserung von Skype for Business erworben. Microsoft Teams und Skype for Business Online. Sie enthalten Umgebungsinformationen wie beispielsweise Gerät und Betriebssystemversion sowie regionale Einstellungen und Spracheinstellungen. Sie umfassen auch Zähler für erfolgreiche und fehlgeschlagene Anmeldeversuche. Hier sehen Sie einige konkrete Beispiele für statistische Daten zu Benutzern, die gesammelt werden:

|**Datentyp**|**Beispiel**|**Hinweise**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|Name des Betriebssystems  <br/> |iPhoneiOS  <br/> ||
|Version des Betriebssystems  <br/> |8,3  <br/> ||
|UserLanguage  <br/> |DE-DE  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |Für die ID wird zweimal ein Hash-Algorithmus verwendet: einmal im Client und einmal im Telemetriedienst. Der Hash-Algorithmus stellt sicher, dass die ID nicht mit einem bestimmten Nutzer verknüpft werden kann.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |Die Geräte-ID ist eine GUID, die nach dem Zufallsprinzip einmalig auf dem Gerät generiert und an den Telemetriedienst gesendet wird.  <br/> |

Die statistischen Daten enthalten KEINE Informationen, anhand derer Ihre Organisation oder Ihre Benutzer identifiziert werden können. Weitere Informationen finden Sie unter [Datenschutzbestimmungen für Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).

Das Sammeln der statistischen Daten zum Nutzer ist standardmäßig aktiviert und kann von Administratoren oder Endbenutzern nicht deaktiviert werden.

## <a name="usage-data"></a>Nutzungsdaten

Zu den Nutzungsdaten zählen beispielsweise Informationen wie die Anzahl der getätigten Anrufe, die Anzahl der gesendeten oder empfangenen Chatnachrichten, die Anzahl der genutzten Telefonkonferenzen, die Nutzungshäufigkeit in Bezug auf verschiedene Features und Stabilitätsprobleme.

Nutzungsdaten enthalten unter Umständen Informationen, anhand derer Ihr Unternehmen identifiziert werden kann, beispielsweise contoso.com. Hier sehen Sie einige konkrete Beispiele für Nutzungsdaten, die gesammelt werden:

|**Datentyp**|**Beispiel**|**Notizen**|
|:-----|:-----|:-----|
|Chatnachrichten gesendet  <br/> |12  <br/> ||
|Chatnachrichten erhalten  <br/> |5  <br/> ||
|Besprechung beigetreten (Versuche)  <br/> |5  <br/> ||
|Besprechung beigetreten (erfolgreiche Versuche)  <br/> |4  <br/> ||
|Anruf-/Besprechungs-Minuten  <br/> |30 Min.  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Dies ist der Name des Unternehmens, das in Office 365 registriert ist. Er wird in Klartext übertragen, also nicht verschleiert.  <br/> |

Die Nutzungsdaten enthalten KEINE Informationen, anhand derer Nutzer identifiziert werden können.

Die Sammlung der Verwendungsdaten ist standardmäßig aktiviert, aber lokale Administratoren können Sie mithilfe der DisableAutomaticSendTracing-Gruppenrichtlinieneinstellung in Skype for Business Server deaktivieren. Das Deaktivieren dieser Einstellung wirkt sich auf alle Benutzer in der Organisation aus. Weitere Informationen finden Sie unter [Konfigurieren von clientbootstrapping-Richtlinien](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .

Benutzer können die Sammlung der Nutzungsdaten nicht aktivieren oder deaktivieren.

Die Telemetrie für die Webseiten der Skype-Besprechungs-App und von Join Launcher kann durch diese Richtlinie gesteuert werden:

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Diese Richtlinie ist standardmäßig auf „False" festgelegt, das heißt, die Telemetriesammlung ist standardmäßig deaktiviert. Diese Einstellung gilt pro Pool und für alle Benutzer, die über die Skype-Besprechungs-App eine Verbindung mit einer Besprechung herstellen, die auf dem jeweiligen Server gehostet wird.

## <a name="error-reporting-data"></a>Fehlerberichtsdaten

Zu den Fehlerberichtsdaten zählen Informationen über Leistung und Zuverlässigkeit, Gerätekonfiguration, Netzwerk-Verbindungsqualität, Fehlercodes, Fehlerprotokolle und Ausnahmen. Hier sehen Sie einige konkrete Beispiele für Fehlerberichtsdaten, die gesammelt werden:

|**Datentyp**|**Beispiel**|**Hinweise**|
|:-----|:-----|:-----|
|Nachrichtenrichtung  <br/> |Eingehend  <br/> ||
|Unterhaltungsstatus  <br/> |Inaktiv  <br/> ||
|Unterhaltungs-Thread-ID  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|UserID  <br/> |amosmarble <br/> |Die ID wird im Klartext übertragen, auf den der Telemetriedienst vor dem Speichern einen Hash-Algorithmus anwendet  <br/> |

Die Fehlerberichterstattungsdaten können außerdem personenbezogene Informationen enthalten, beispielsweise die IP-Adresse des Benutzers und den SIP-URI (Session Initiation Protocol Uniform Resource Identifier). Unter [Datenschutzbestimmungen für Skype for Business](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) wird ausführlich erklärt, welche Daten gesammelt werden.

Für die Fehlerberichterstattung müssen zwei Voraussetzungen erfüllt sein:

- Die DisableAutomaticSendTracing-Gruppenrichtlinieneinstellung ist auf dem Server oder im Mandanten-Admin Center auf "false" festgelegt (Dies ist der Standardzustand). Weitere Informationen finden Sie unter [Konfigurieren von clientbootstrapping-Richtlinien](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .
    
- Endbenutzer können sich auf der Registerkarte "Allgemein" einzeln einwählen ![(Klicken Sie auf das Zahnrad ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) Symbol ein Symbol, das ein Zahnrad darstellt, und dann wird das Dialogfeld " **Optionen** " mit der Registerkarte " **Allgemein** " angezeigt) im Skype for Business-Client.
    
 
![Screenshot des Kontrollkästchens ' Datensammlung ' im Dialogfeld ' Optionen '](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Für die Skype-Besprechungs-App steuert „MeetingUxEnableTelemetry" außerdem die Fehlerberichterstattung, obwohl für Abstürze unter Windows die Watson-Einstellungen das Hochladen von Absturzinformationen steuern. Es gibt für die Skype-Besprechungs-App keine Benutzereinstellung wie im Dialogfeld des Desktopclients.

Weitere Informationen finden Sie unter [Festlegen von allgemeinen Optionen in Skype for Business](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).

Informationen zur Einrichtung Ihres Netzwerks finden Sie unter [Einrichten Ihres Netzwerks für Skype for Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66).

Wenn Sie Office 365 über 21Vianet in China nutzen, finden Sie weiterführende Informationen unter [Set up your network for Lync Online](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Verwandte Themen
[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
