---
title: Telefonnummern für Audiokonferenzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned.
ms.openlocfilehash: 9b1fca6a576a9de77e74bcab8df740b5106cf5bc
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="phone-numbers-for-audio-conferencing"></a>Telefonnummern für Audiokonferenzen

When you are setting up **Audio Conferencing** for Skype for Business and Microsoft Teams, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> Es gibt keine Ressource, die eine Liste aller Einwahlnummern für Audiokonferenzen enthält. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Verwenden Sie die Listen für **Land/Region**, **Bundesland/Kanton** und **Ort**, um die Suchergebnisse zu filtern. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>Audio Conferencing coverage and pricing

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). For pricing information, see 
  
[Preise für Audiokonferenzen](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>Einwahltelefonnummern in einer Besprechungseinladung

When a Skype for Business Online or Microsoft Teams user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
Sie können weitere Einwahlnummern anzeigen, indem Sie in der Besprechungseinladung auf **Lokale Rufnummer suchen** klicken.
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>Dial-in phone numbers set on an audio conferencing bridge

Es gibt zwei Arten von Audiokonferenz-Telefonnummern, die Ihrer Konferenzbrücke zugewiesen sein können: **Freigegeben** und **Dediziert**. Beide Arten von Nummern können von allen Anrufern verwendet werden, um an Audiobesprechungen in Ihrer Organisation teilzunehmen.
  
 **Dedizierte Telefonnummern** sind Telefonnummern, die nur den Benutzern in Ihrer Organisation zur Verfügung stehen. Sie können die Sprachen ändern, die verwendet werden, wenn jemand unter diesen Nummern anruft.
  
 **Freigegebene Telefonnummern** sind Telefonnummern, die an andere Office 365-Organisationen freigegeben werden können. Sie können die Sprachen, die verwendet werden, wenn jemand unter diesen Nummern anruft, nicht ändern.
  
Nur die Standardtelefonnummer für Audiokonferenzen, die einem Organisator zugewiesen ist, ist in der Besprechungseinladung enthalten. Anrufer können aber jede der Telefonnummern, die Ihrer Konferenzbrücke zugewiesen sind, für die Teilnahme an einer Besprechung verwenden. Die Liste der Telefonnummern, die für die Teilnahme an einer Besprechung verwendet werden können, befindet sich unter dem Link **Lokale Rufnummer suchen**, der in jeder Besprechungseinladung enthalten ist.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>Automatisch zugewiesene Audiokonferenz-Telefonnummern

Freigegebene Audiokonferenz-Telefonnummern werden Organisationen automatisch zugewiesen, wenn sie für Audiokonferenzen aktiviert sind. Bei der Zuweisung der Telefonnummern wird eine Telefonnummer als Standardtelefonnummer der Konferenzbrücke zugewiesen. Die als Standardtelefonnummer der Brücke zugewiesene Telefonnummer stammt aus dem Land/der Region der Organisation.
  
> [!NOTE]
> The country or region location of your organization can be found by signing in to the **Office 365 admin center** and looking under **Organization Profile**. 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. Gebührenfreie Telefonnummern für diese Standorte stehen je nach verfügbarem Bestand zur Verfügung. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).
  
To see a list of those countries/regions that have phone numbers automatically assigned to organizations, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- To see the list of supported languages for audio conferencing, see [Audio Conferencing supported languages](audio-conferencing-supported-languages.md).
    
- Mithilfe des Cmdlets [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) können Sie die dedizierten Telefonnummern für Audiokonferenzen für Ihre Organisation anzeigen.
    
- Mit dem Cmdlet [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) können Sie die Sprachen anzeigen, die für eine fest zugeordnete Einwahltelefonnummer festgelegt werden können.
    
- Für jede Audiokonferenz-Telefonnummer können Sie bis zu vier Sprachen einrichten - eine primäre und drei sekundäre. Sie können die Sprachen auch für eine dedizierte Audiokonferenz-Telefonnummer festlegen.
    
- To set the dial-in phone number for a user, see [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>See Also

[Testen oder Erwerben von Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
