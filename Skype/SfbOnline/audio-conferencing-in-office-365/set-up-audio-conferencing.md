---
title: Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Erfahren Sie, wie Sie Einwahl- oder Audiokonferenzen für die Personen in Ihrem Unternehmen einrichten, die an Telefonkonferenzen teilnehmen müssen. '
ms.openlocfilehash: 52872b9995d5973ee872e3105c870ccf7bb07abc
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703484"
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams

Manchmal müssen Personen in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Skype for Business und Microsoft Teams enthalten genau für diese Situation die Funktion Audiokonferenz! Personen können über ein Telefon in Skype für Unternehmen oder Microsoft Teams-Besprechungen anrufen, anstatt die Skype für Unternehmen oder Microsoft Teams-App auf einem mobilen Gerät oder PC zu verwenden. 
  
Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten. Besprechungsteilnehmer, die sich einwählen, benötigen keine ihnen zugewiesenen Lizenzen oder andere Einstellungen.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a>Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind
<a name="__top"> </a>


Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten. 
 
## <a name="step-2-get-and-assign-licenses"></a>Schritt 2: Abrufen und Zuweisen von Lizenzen
 
1. Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichtet. Informationen dazu, welche Lizenzen Sie für Audiokonferenzen kaufen müssen und was diese kosten, erhalten Sie in der [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
        
2. Nachdem Sie die Audiokonferenz-Lizenzen erworben haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten werden. nrufpläneSiehe [Zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die Sie für die Personen in Ihrer Organisation erworben haben, die Besprechungen planen oder leiten werden.
    
3. Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben. Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
> [!NOTE]
> Sie können auch pay-per-minute Audiokonferenzen einrichten. Klicken Sie [hier](../skype-for-business-and-microsoft-teams-add-on-licensing/audio-conferencing-pay-per-minute.md), um weitere Informationen zu deren Verwendung zu erhalten.

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a>Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern
<a name="__top"> </a>

Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern. Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen. Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten: 
  
- **Über das Skype for Business Admin Center.** Für einige Länder/Regionen können Sie Servicenummern für Ihre Konferenzbrücken über das Skype for Business Admin Center erhalten, siehe [Servicetelefonnummern erhalten](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
    
- **Portieren der bestehenden Servicenummern.** Portieren oder übertragen Sie Ihre vorhandenen Telefonnummern von Ihrem derzeitigen Dienstanbieter oder Netzbetreiber zu Office 365. Über [Übertragen von Telefonnummern zu Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) oder [Rufnummern für Ihre Organisation verwalten](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) erhalten Sie weitere hilfreiche Informationen.  
  
- **Verwenden Sie ein Anforderungsformular für neue Nummern.** Manchmal können Sie (je nach Land/Region) Ihre neuen Nummern nicht über das Skype for Business Admin Center beziehen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahlen. In diesem Fall müssen Sie ein Formular herunterladen und an uns senden. Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a>Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke
<a name="__top"> </a>

Sobald Sie Ihre gebührenpflichtige und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten, müssen Sie die Nummern zuweisen, damit sie für die Einladungen zu den Besprechungen verwendet werden können.  

Um eine neue Rufnummer Ihrer Audiokonferenzbrücke zuzuweisen:

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Center**

 Wechseln Sie zu der **Office 365 Admin Center** > **Admin Centers** > **Skype für Unternehmen** > **VoIP** > **Telefonnummern**, wählen Sie die Rufnummer ein, und klicken Sie auf **zuweisen**.

Weitere Informationen finden Sie unter [Ihrer Audiokonferenzbrücke eine neuen Rufnummer zuweisen](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a>Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest
<a name="__top"> </a>

Als Nächstes möchten Sie [Auto-Attendant-Sprachen für Audiokonferenzen einstellen](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md), die der Auto-Attendant verwendet, um einen Anrufer zu begrüßen, wenn er sich mit einer Telefonnummer für Audiokonferenzen einwählt. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

Gehen Sie im Dashboard auf**Besprechungen** > **Konferenzbrücken**, wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Center**

Wechseln Sie auf **Office 365 Admin Center** > **Admin Centers** > **Skype für Business** > **Audiokonferenzen** > **Microsoft Brückeneinstellungen**, wählen Sie die Telefonnummer der Konferenzbrücke und klicken Sie dann auf **Sprachen einstellen**.

## <a name="step-6-set-your-conferencing-bridge-settings"></a>Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen
<a name="__top"> </a>
    
Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern. 

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

Wechseln Sie über das Dashboard auf **Besprechungen** > **Konferenzbrücken** > **Brückeneinstellungen**. Der **Brücke**-Einstellungsbereich wird geöffnet. Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung von Skype for Business Admin Center**

Wechseln Sie auf **Office 365 Admin Center** > **Admin Centers** > **Skype für Business** > **Audiokonferenzen** > **Microsoft Brückeneinstellungen**. Die Seite **Microsoft Brückeneinstellungen** wird geöffnet. Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](../audio-conferencing-in-office-365/change-the-settings-for-an-audio-conferencing-bridge.md).

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a>Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten

Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.

Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen. Gehen Sie dazu wie folgt vor:

![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

Klicken Sie aus dem Dashboard auf **Benutzer**, wählen Sie den Benutzer aus der Liste, klicken Sie auf **Bearbeiten**, klicken Sie auf **Bearbeiten**, neben **Audiokonferenzen**und wählen Sie dann im Bereich **Audiokonferenzen** eine Nummer für die **gebührenpflichtige** und **gebührenfreie** Liste der Telefonummern.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung von Skype for Business Admin Center**

Wechseln Sie auf **Office 365 Admin Center** > **Skype für Business** > **Audiokonferenzen** > **Benutzer**, wählen Sie Benutzer aus der Liste aus, und klicken Sie auf **Bearbeiten**. Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).


## <a name="step-8-set-up-meeting-invitations-optional"></a>Schritt 8: Besprechungseinladungen einrichten (optional)
<a name="__top"> </a>
 
Die für den Nutzer festgelegten Einwahlnummern werden automatisch den Besprechungseinladungen hinzugefügt, die Teilnehmern zugesendet werden. Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten. Siehe [Besprechungseinladungen anpassen](../set-up-skype-for-business-online/customize-meeting-invitations.md).
   
## <a name="related-topics"></a>Verwandte Themen

[Allgemeine Fragen zur Audiokonferenz](audio-conferencing-common-questions.md)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md)
  
[Optionen für Onlinebesprechungen und Telefonkonferenzen festlegen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
