---
title: Planen der Ansageanwendung in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planung für die ansageanwendung in Skype für Business Server Enterprise-VoIP, konfiguriert die auszuführende Aktion, mit dem Telefonanrufe an nicht zugewiesene Telefonnummern in Ihrer Organisation. Es konfiguriert, was mit nicht zugewiesenen Telefonnummern in Ihren Organisationen passiert und beinhaltet Audiodateianforderungen.
ms.openlocfilehash: c7ed700c749f1d5692b78c931e225fee5d0497be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-the-announcement-application-in-skype-for-business-2015"></a>Planen der Ansageanwendung in Skype for Business 2015
 
Planung für die ansageanwendung in Skype für Business Server Enterprise-VoIP, konfiguriert die auszuführende Aktion, mit dem Telefonanrufe an nicht zugewiesene Telefonnummern in Ihrer Organisation. Es konfiguriert, was mit nicht zugewiesenen Telefonnummern in Ihren Organisationen passiert und beinhaltet Audiodateianforderungen.
  
Die Skype für Business Server ansageanwendung können Sie die Handhabung von Eingehende Telefonanrufe konfigurieren, wenn die gewählte Nummer für Ihre Organisation gültig ist, aber nicht für einen Benutzer oder ein Telefon zugewiesen wird. Sie können diese Anrufe an ein vorab festgelegtes Ziel (Rufnummer, SIP-URI oder Voicemail) übergeben oder eine Audioansage wiedergeben oder beides. Mithilfe der Ansageanwendung können Sie Situationen verhindern, in denen sich ein Anrufer verwählt und ein Besetztzeichen hört oder der SIP-Client eine Fehlermeldung erhält. Dieser Abschnitt bietet Informationen, die speziell für die ansageanwendung sind Planung
  
Bei der Bereitstellung der ankündigungsanwendung müssen Sie einen Tabelle mit nicht zugewiesenen Nummern konfigurieren, der die Aktion ausgeführt werden, wenn jemand eine nicht zugewiesene Nummer anwählt bestimmt. Die Tabelle für nicht zugewiesene Nummern enthält Bereiche von Rufnummern, die für die Organisation gültig sind und gibt an, welche Anwendung Ankündigung jeweiligen Bereich behandelt. Wenn ein Anrufer eine Telefonnummer, die für Ihre Organisation gilt jedoch nicht für alle Benutzer zugewiesen ist wählt, Skype für die Zahl in der Tabelle nicht zugewiesener Nummern routing, Business Server nachschlägt identifiziert den Bereich liegt der Anzahl und leitet den Anruf an die Ansageanwendung für diesen Bereich angegeben. Der ankündigungsanwendung den Anruf annimmt und spielt eine audio-Nachricht (falls Sie dazu konfiguriert) und trennt den Anruf oder an ein vordefiniertes Ziel, wie beispielsweise an einen Operator überträgt. Skype für Business Server-Verwaltungsshell-Cmdlets können mehrere audio Nachrichten zu konfigurieren oder um Ziele zu übertragen.
  
Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie sie verwenden möchten. Wenn Sie über bestimmte Nummern verfügen, die nicht mehr verwendet werden, und individuelle Nachrichten für jede dieser Nummern wiedergeben möchten, können Sie diese spezifischen Nummern in die Tabelle nicht zugewiesener Rufnummern eingeben. Wenn Sie beispielsweise die Nummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle eingeben und einer Ansage zuordnen, in der die neue Rufnummer bereitgestellt wird. Um eine allgemeine Nachricht für Anrufer wiederzugeben, die eine nicht zugewiesene Nummer wählen (z. B. für Mitarbeiter, die nicht mehr für Ihre Organisation tätig sind), können Sie Bereiche für alle gültigen Durchwahlnummern in Ihrer Organisation angeben. Die Tabelle nicht zugewiesener Rufnummern wird aufgerufen, sobald ein Anrufer eine Nummer wählt, die gegenwärtig nicht zugewiesen ist.
  
## <a name="deployment-and-requirements"></a>Bereitstellungen und Anforderungen

Ankündigung der Anwendung wird automatisch mit der Anwendung "Reaktionsgruppe" installiert. Die Anwendungen Ankündigung und Reaktionsgruppe sind Standardkomponenten einer Enterprise-VoIP-Bereitstellung: bei der Bereitstellung von Enterprise-VoIP werden beide dieser Anwendungen automatisch bereitgestellt. 
  
### <a name="software-requirements"></a>Softwareanforderungen

Alle Front-End-Server oder Standard Edition-Server, die die ankündigungsanwendung ausgeführt werden müssen die Windows Media Format-Laufzeitkomponente für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Windows Server 2012-Server installiert haben oder Windows Server 2012 R2. Die Windows Media Format-Laufzeitkomponente ist für Windows Server 2008 R2 als Teil des Windows Desktop Experience installiert. Windows Media Format-Laufzeitkomponente oder Microsoft Media Foundation ist erforderlich für Windows Media Audio (WMA) Dateien, die der ankündigungsanwendung spielt für Ankündigungen und Musik. 
  
### <a name="port-requirements"></a>Portanforderungen

Die ankündigungsanwendung verwendet **Port 5071** für SIP-überwachungsanforderungen verwendet.
    
> [!NOTE]
> Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie unter der Skype Business Server-Verwaltungsshell-Dokumentation.
  
### <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Der ankündigungsanwendung unterstützt WAV-Dateiformat und Windows Media Audio (WMA) Dateiformat für Musik und Ankündigungen. Audiodateianforderungen für die ansageanwendung sind die gleichen wie für die Anwendung "Reaktionsgruppe". Weitere Informationen hierzu finden Sie unter [Technische Anforderungen für Reaktionsgruppen](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).
  

