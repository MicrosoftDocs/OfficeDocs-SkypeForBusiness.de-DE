---
title: "Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
description: "See how to select the auto-attendant lanugages for a dial-in conferencing number."
---

# Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Die Audio-Konferenzen automatische Telefonzentrale für Skype for Business und Microsoft Teams kann Einwahlnummern Anrufer in einer Reihe von verschiedenen Sprachen begrüßen, wenn sie an eine Besprechung teilnehmen.
  
Wählen Sie eine primäre Sprache und bis zu vier sekundäre Sprachen. Die primäre Sprache, die Sie festlegen, wird zuerst verwendet. Die sekundären Sprachen werden von der automatischen Telefonzentrale in der von Ihnen gewählten Reihenfolge verwendet. 
  
> [!NOTE]
>  Sie können die Sprachen nur für inländische Einwahltelefonnummern konfigurieren.
  
## Festlegen der Konferenzen automatische Telefonzentrale Sprachen

Sie müssen globaler [Informationen zu Administratorrollen von Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) oder[Informationen zu Administratorrollen von Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) sein, um diesen Schritt ausführen zu können.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In der **Skype für Business Administrationscenter** im linken Navigationsbereich wechseln Sie zu **Konferenzen Audio**, und klicken Sie dann auf **Microsoft Bridge**.
    
4. Klicken Sie im Bereich Aktion wählen Sie die Telefonnummer für den Audiokonferenzanbieter aus der Liste, klicken Sie auf **Sprachen festlegen**.
    
5. Klicken Sie auf der Seite **Sprachen festlegen** auf das Dropdown-Feld unter **Primäre Sprache**, um die komplette Liste verfügbarer Sprachen anzuzeigen. Klicken Sie nach Bedarf auf jedes der Dropdown-Felder **Sekundäre Sprachen**, um die sekundäre Sprache auszuwählen.
    
    > [!NOTE]
    > Die primäre Sprache und die sekundären Sprachen, die unterstützt werden, werden aufgeführt. Die Reihenfolge, in der Sie Ihre Auswahl in der Dropdownliste treffen, bestimmt die Reihenfolge, in der die Sprachen Anrufern präsentiert werden. 
  
6. Klicken Sie auf **Speichern**.
    
## Was sollte ich noch wissen?

- Um die Liste der unterstützten Sprachen für Audio Konferenzen angezeigt wird, finden Sie unter [Audiokonferenzanbieter unterstützte Sprachen](audio-conferencing-supported-languages.md).
    
- Sprachen können für dedizierte, aber nicht für freigegebene Telefonnummern festgelegt werden.
    
- Um einer Liste der Länder/Regionen finden Sie unter dieser Audiokonferenzanbieter in Office 365 mithilfe von Microsoft, wie der Anbieter verfügbar ist, finden Sie unter [Telefonnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md).
    
## Sie möchten Windows PowerShell verwenden?

Wenn Sie diesen Schritt automatisieren möchten, können Sie die Cmdlets [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) und[Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) verwenden.
  
Weitere Informationen finden Sie unter [Mithilfe von Windows PowerShell allgemeine Skype für Business Online-Verwaltungsaufgaben ausführen](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

