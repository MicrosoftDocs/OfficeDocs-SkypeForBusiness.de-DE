---
title: Verwalten von Exchange Unified Messaging und gehosteten Voicemails
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Verwenden Sie PowerShell zum Verwalten von Exchange Unified Messaging-Funktionen wie automatische Telefonzentrale Und Abonnentenzugriff und gehostete Voicemail in Skype for Business Online.
ms.openlocfilehash: 393b0a43cb55462006ef7701396a3b7840032fb4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113201"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Verwalten von Exchange Unified Messaging und gehosteten Voicemails

Sie können Exchange Unified Messaging und gehostete Voicemails in Skype for Business Online mit einer Reihe von Cmdlets verwalten.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Verwalten von Exchange Unified Messaging und gehosteten Voicemails

Die folgenden Cmdlets können zum Verwalten von Exchange Unified Messaging (UM) und Richtlinien für gehostete Voicemails verwendet werden:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Beschreibung**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](/powershell/module/skype/Get-CsExUmContact) <br/><br/> [New-CsExUmContact](/powershell/module/skype/New-CsExUmContact) <br/> <br/>[Remove-CsExUmContact](/powershell/module/skype/Remove-CsExUmContact) <br/> <br/>[Set-CsExUmContact](/powershell/module/skype/Set-CsExUmContact) <br/> | Erstellt und verwaltet Kontaktobjekte, die für die automatische Telefonzentrale und für Abonnentenzugriffsdienste verwendet werden, wenn Exchange UM als gehosteter Dienst bereitgestellt ist.  <br/><br/> Skype for Business Online stellt gemeinsam mit Exchange UM verschiedene Funktionen im Zusammenhang mit VoIP bereit, darunter automatische Telefonzentrale und Abonnentenzugriff. Mit der automatischen Telefonzentrale können Anrufe automatisch angenommen und an die richtige Person weitergeleitet werden. Über den Abonnentenzugriff können Benutzer eine Verbindung mit Exchange UM herstellen und E-Mails, Sprachnachrichten, Kontakte und Kalenderinformationen abrufen.<br/><br/> Wenn Exchange UM als gehosteter Dienst bereitgestellt ist, müssen Kontaktobjekte, die für die automatische Telefonzentrale und für Abonnentenzugriffsdienste verwendet werden, mit Microsoft PowerShell erstellt werden. Diese Objekte werden mit den **CsExUmContact** -Cmdlets erstellt und verwaltet.<br/> |
| [Get-CSHostedVoicemailPolicy](/powershell/module/skype/Grant-CsHostedVoicemailPolicy) <br/> <br/>[Grant-CSHostedVoicemailPolicy](/powershell/module/skype/Set-CsTenantPublicProvider) <br/>                                                                                                                                                | Verwaltet in der Organisation verwendete Richtlinien für gehostete Voicemails. Richtlinien für gehostete Voicemails legen fest, wie nicht angenommene Anrufe an den Exchange UM-Dienst weitergeleitet werden. Diese Richtlinien wirken sich nur auf Benutzer aus, die für gehostete Voicemails in Exchange UM aktiviert sind.    <br/><br/> Um zu überprüfen, ob ein Benutzer für gehostete Voicemails aktiviert ist, führen Sie an der PowerShell-Eingabeaufforderung etwa den folgenden Befehl aus.  <br/> \`Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Verwandte Themen
[Einrichten Ihres Computers für skype for business online management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
