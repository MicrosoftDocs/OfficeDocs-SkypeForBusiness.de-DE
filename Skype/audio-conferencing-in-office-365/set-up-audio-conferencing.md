---
title: "Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365P_DialInConfDesc
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9

description: "Learn how to set up dial-in or audio conferencing (PSTN Conferencing) for the people in your business who need to join conference calls using a phone. "
---

# Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams

Manchmal müssen Mitarbeiter in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Für genau diese Situation enthalten Skype for Business und Microsoft Teams die Audiokonferenzfunktion. Teilnehmer können sich mit einem Telefon in Skype for Business- oder Microsoft Teams-Besprechungen einwählen, anstatt die Skype for Business- oder Microsoft Teams-App auf einem Mobilgerät oder PC zu verwenden. 
  
Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Für Besprechungsteilnehmer, die sich einwählen, müssen Sie keine persönlichen Lizenzen zuweisen und nichts konfigurieren.
  
Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Audio Conferencing common questions](audio-conferencing-common-questions.md).
  
## Schritt 1: Lizenzen kaufen und zuweisen
<a name="__top"> </a>

Sie müssen [Informationen zu Administratorrollen von Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) sein, um diesen Schritt ausführen zu können.
  
1. Informieren Sie sich, ob Audiokonferenzen in Office 365 in Ihrem Land/Ihrer Region verfügbar sind. [Länder und Region Verfügbarkeit für Audio - Konferenzen und Aufrufen-Pläne](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md). 
    
2. Informieren Sie sich, welche Lizenzen Sie für Audiokonferenzen kaufen müssen und was diese kosten. Lesen Sie [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), und kaufen Sie die Lizenzen. 
    
3. [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), das heißt den Mitarbeitern in Ihrer Organisation, die Besprechungen planen oder leiten werden. 
    
4. Falls Sie Add-On-Lizenzen für **Audiokonferenzen** und Lizenzen für Guthaben für Kommunikationen erworben haben, weisen Sie diese ebenfalls zu. Anweisungen hierzu finden Sie unter[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## Schritt 2: Auswählen des Audiokonferenzanbieters
<a name="__top"> </a>

Ein Audiokonferenzanbieter stellt eine  *Audiokonferenzbrücke*  bereit. Die Konferenzbrücke legt Ihre Einwahltelefonnummern, PINs und Konferenzkennungen für Besprechungen fest. Entscheiden Sie, ob Sie Microsoft oder einen Drittanbieter für Audiokonferenzen nutzen möchten:
  
> [!NOTE]
> Microsoft Teams-Benutzer können keinen Drittanbieter für Audiokonferenzen verwenden. 
  
- **Microsoft als Audiokonferenzanbieter**: Die einfachste Lösung für Audiokonferenzen erhalten Sie, wenn Sie Microsoft als Audiokonferenzanbieter auswählen.
    
- **Drittanbieter als Audiokonferenzanbieter**: Wenn Sie sich in einem Land/einer Region befinden, in dem bzw. in der Audiokonferenzen in Office 365 nicht verfügbar sind, die Servicequalität aufgrund des Standorts schlecht ist oder Sie einen bestehenden Vertrag haben, wählen Sie einen Drittanbieter für Audiokonferenzen aus. Um einen Anbieter zu finden, gehen Sie zu **[Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530)**.
    
> [!TIP]
> Es kann vorkommen, dass in Ihrer Organisation einige Mitarbeiter Microsoft als Audiokonferenzanbieter und andere einen Drittanbieter nutzen. Das ist jedoch komplizierter einzurichten und zu verwalten. 
  
Einen detaillierten Vergleich zwischen Microsoft und einem Drittanbieter als Audiokonferenzanbieter finden Sie unter [Vergleich zwischen Audiokonferenzanbietern](compare-audio-conferencing-providers.md). 
  
## Schritt 3: Zuweisen des Audiokonferenzanbieters für Personen, die Besprechungen leiten oder planen
<a name="__top"> </a>

Nachdem Sie sich für einen Audiokonferenzanbieter entschieden haben, müssen Sie den Anbieter Personen in Ihrer Organisation zuweisen, die Besprechungen leiten oder planen. Führen Sie eine der folgenden Aktionen aus: 
  
- [Zuweisen von Microsoft als Audiokonferenzanbieter](assign-microsoft-as-the-audio-conferencing-provider.md)
    
- [Zuweisen eines Drittanbieters für Audiokonferenzen](assign-a-third-party-as-the-audio-conferencing-provider.md) .
    
## Schritt 4: Besprechungseinladungen einrichten
<a name="__top"> </a>

Die folgenden Schritte sind **optional**, werden jedoch von vielen Administratoren gerne selbst durchgeführt:
  
1. [Anpassen von Besprechungseinladungen](../set-up-skype-for-business-online/customize-meeting-invitations.md) . Die für den Benutzer festgelegten Einwahlnummern werden automatisch den Einladungen für Besprechungen hinzugefügt, die Teilnehmern zugesendet werden. Sie können jedoch Ihre eigenen Links zu Hilfe- und rechtlichen Texten, eine Textnachricht und eine kleine Unternehmensgrafik hinzufügen.
    
2. [Festlegen der in Einladungen enthaltenen Audiokonferenz-Telefonnummern für Besprechungsorganisatoren](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md) . Diese Telefonnummer wird in der Besprechung angezeigt, die der Benutzer plant.
    
3. [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing.md) , in denen die automatische Konferenzzentrale für Audiokonferenzen Anrufer begrüßt, die die Telefonnummer einer Audiokonferenz wählen. Dieser Schritt gilt nur, wenn Sie Microsoft als Audioanbieter verwenden.
    
4. [Konfigurieren der Länge der PIN für Einwahl-Besprechungen](set-the-length-of-the-pin-for-audio-conferencing-meetings.md) .
    
> [!NOTE]
> Diese Funktion steht Kunden noch nicht zur Verfügung, die „Office 365 operated by 21Vianet" in China verwenden. Weitere Informationen hierzu finden Sie unter [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 
  
||
|:-----|
|![Symbol für LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Neu bei Office 365?**         Entdecken Sie kostenlose Videokurse für **Office 365-Administratoren und IT-Experten**, bereitgestellt von LinkedIn Learning. |
   
## Siehe auch
<a name="__top"> </a>

#### Weitere Ressourcen

[Audio Conferencing common questions](audio-conferencing-common-questions.md)
  
[Einrichten von Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md)
  
[Festlegen von Optionen für Onlinebesprechungen und Telefonkonferenzen](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

