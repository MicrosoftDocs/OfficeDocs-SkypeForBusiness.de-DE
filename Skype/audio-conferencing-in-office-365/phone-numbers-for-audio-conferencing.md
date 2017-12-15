---
title: "Telefonnummern für Audiokonferenzen"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7

description: "Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned."
---

# Telefonnummern für Audiokonferenzen

Wenn Sie **Audiokonferenzen** für Skype for Business und Microsoft Teams einrichten, werden Ihrer Organisation automatisch Einwahltelefonnummern zugewiesen. Mit den folgenden Optionen können Sie die Telefonnummern anzeigen, die Ihrer Audiokonferenzbrücke zugewiesen sind: **Skype for Business Admin Center** > **Audio conferencing** (Audiokonferenz) > **Microsoft Bridge**. Weitere Informationen finden Sie unter [Anzeigen einer Liste mit Einwahlnummern für Einwahlkonferenzen](see-a-list-of-audio-conferencing-numbers.md).
  
## Verfügbarkeit von Audiokonferenzen

Eine vollständige Liste aller Länder/Regionen und Städte, in denen Audiokonferenzen verfügbar sind, finden Sie unter [Sind in meinem Land bzw. meiner Region PSTN-Konferenzen mit Telefonnummern verfügbar?](https://support.office.com/article/1096d81e-7e14-488c-95d8-b8322e39c059).
  
## Einwahltelefonnummern in einer Besprechungseinladung

Wenn ein Skype for Business Online- oder Microsoft Teams-Benutzer in Outlook oder Outlook Web App eine Besprechung plant, ist die für den Benutzer festgelegte Standardnummer für Audiokonferenzen in der Besprechungseinladung enthalten. Wenn Sie für einen oder mehrere Benutzer eine andere Standardnummer auswählen möchten, können Sie dies ändern, indem Sie **Skype for Business Admin Center** > **Audio conferencing** (Audiokonferenz) > **Benutzer** auswählen. Weitere Informationen finden Sie unter[Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
Sie können weitere Einwahlnummern anzeigen, indem Sie in der Besprechungseinladung auf **Lokale Rufnummer suchen** klicken.
  
## Für eine Audiokonferenzbrücke festgelegte Einwahltelefonnummern

Es gibt zwei Arten von Audiokonferenz-Telefonnummern, die Ihrer Konferenzbrücke zugewiesen sein können: **Freigegeben** und **Dediziert**. Beide Arten von Nummern können von allen Anrufern verwendet werden, um an Audiobesprechungen in Ihrer Organisation teilzunehmen.
  
 **Dedizierte Telefonnummern** sind Telefonnummern, die nur den Benutzern in Ihrer Organisation zur Verfügung stehen. Sie können die Sprachen ändern, die verwendet werden, wenn jemand unter diesen Nummern anruft.
  
 **Freigegebene Telefonnummern** sind Telefonnummern, die an andere Office 365-Organisationen freigegeben werden können. Sie können die Sprachen, die verwendet werden, wenn jemand unter diesen Nummern anruft, nicht ändern.
  
Nur die Standardtelefonnummer für Audiokonferenzen, die einem Organisator zugewiesen ist, ist in der Besprechungseinladung enthalten. Anrufer können aber jede der Telefonnummern, die Ihrer Konferenzbrücke zugewiesen sind, für die Teilnahme an einer Besprechung verwenden. Die Liste der Telefonnummern, die für die Teilnahme an einer Besprechung verwendet werden können, befindet sich unter dem Link **Lokale Rufnummer suchen**, der in jeder Besprechungseinladung enthalten ist.
  
## Automatisch zugewiesene Audiokonferenz-Telefonnummern

Freigegebene Audiokonferenz-Telefonnummern werden Organisationen automatisch zugewiesen, wenn sie für Audiokonferenzen aktiviert sind. Bei der Zuweisung der Telefonnummern wird eine Telefonnummer als Standardtelefonnummer der Konferenzbrücke zugewiesen. Die als Standardtelefonnummer der Brücke zugewiesene Telefonnummer stammt aus dem Land/der Region der Organisation.
  
> [!NOTE]
> Das Land bzw. die Region, in dem bzw. in der sich Ihre Organisation befindet, finden Sie nach der Anmeldung beim **Office 365 Admin Center** unter **Company Profile** (Firmenprofil).
  
> [!CAUTION]
> Aufgrund der eingeschränkten Verfügbarkeit von gebührenpflichtigen Telefonnummern in Venezuela, Indonesien und den Vereinigten Arabischen Emiraten wird Organisationen aus diesen Ländern/Regionen nicht automatisch eine gebührenpflichtige Audiokonferenz-Telefonnummer zugewiesen. Gebührenfreie Telefonnummern für diese Standorte stehen je nach verfügbarem Bestand zur Verfügung. 
  
Dedizierte Audiokonferenz-Telefonnummern sind Servicenummern, die Sie erhalten und dann Ihrer Organisation zuweisen können. Diese Servicenummern finden Sie im **Skype for Business Admin Center**. Einzelheiten hierzu finden Sie unter [Abrufen von Skype for Business-Leistungsnummern](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md).
  
Eine Liste der unterstützten Länder/Regionen, in denen Organisationen automatisch Telefonnummern zugewiesen werden, finden Sie unter [Länder und Region Verfügbarkeit für Audio - Konferenzen und Aufrufen-Pläne](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md).
  
## Was sollten Sie noch wissen?

- Unter [Audiokonferenzanbieter unterstützte Sprachen](audio-conferencing-supported-languages.md) finden Sie eine Liste der unterstützten Sprachen für Audiokonferenzen.
    
- Mithilfe des Cmdlets [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) können Sie die dedizierten Telefonnummern für Audiokonferenzen für Ihre Organisation anzeigen.
    
- Mit dem Cmdlet [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) können Sie die Sprachen anzeigen, die für eine fest zugeordnete Einwahltelefonnummer festgelegt werden können.
    
- Für jede Audiokonferenz-Telefonnummer können Sie bis zu vier Sprachen einrichten - eine primäre und drei sekundäre. Sie können die Sprachen auch für eine dedizierte Audiokonferenz-Telefonnummer festlegen.
    
- Angaben zum Festlegen der Einwahltelefonnummer für einen Benutzer finden Sie unter [Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
    
||
|:-----|
|![Symbol für LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Neu bei Office 365?**         Entdecken Sie kostenlose Videokurse für **Office 365-Administratoren und IT-Experten**, bereitgestellt von LinkedIn Learning. |
   
## Siehe auch

#### Weitere Ressourcen

[Einwahlkonferenzen in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

