---
title: Verwalten von Exchange Unified Messaging und gehosteten Voicemails
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 707198df-df85-4833-9c15-aa29b71f085c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Use PowerShell to manage Exchange Unified Messaging capabilities such as Auto Attendant and Subscriber Access and hosted voicemail in Skype for Business Online.
ms.openlocfilehash: d00328ad50bdcfeea326255d1dcd6d22daa9a3a4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372854"
---
# <a name="manage-exchange-unified-messaging-and-hosted-voicemail"></a>Verwalten von Exchange Unified Messaging und gehosteten Voicemails

Sie können Exchange Unified Messaging und gehostete Voicemails in Skype for Business Online mit einer Reihe von Cmdlets verwalten.
  
## <a name="manage-exchange-unified-messaging-and-hosted-voice-mail"></a>Verwalten von Exchange Unified Messaging und gehosteten Voicemails

Die folgenden Cmdlets können zum Verwalten von Exchange Unified Messaging (UM) und Richtlinien für gehostete Voicemails verwendet werden:
  

| **Cmdlet**                                                                                                                                                                                                                                                                                                                        | **Beschreibung**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Get-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849628) <br/><br/> [New-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849629) <br/> <br/>[Remove-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849630) <br/> <br/>[Set-CsExUmContact](https://go.microsoft.com/fwlink/p/?linkid=849631) <br/> | Erstellt und verwaltet Kontaktobjekte, die für die automatische Telefonzentrale und für Abonnentenzugriffsdienste verwendet werden, wenn Exchange UM als gehosteter Dienst bereitgestellt ist.  <br/><br/> Skype for Business Online stellt gemeinsam mit Exchange UM verschiedene Funktionen im Zusammenhang mit VoIP bereit, darunter automatische Telefonzentrale und Abonnentenzugriff. Mit der automatischen Telefonzentrale können Anrufe automatisch angenommen und an die richtige Person weitergeleitet werden. Über den Abonnentenzugriff können Benutzer eine Verbindung mit Exchange UM herstellen und E-Mails, Sprachnachrichten, Kontakte und Kalenderinformationen abrufen.<br/><br/> Wenn Exchange UM als gehosteter Dienst bereitgestellt ist, müssen Kontaktobjekte, die für die automatische Telefonzentrale und für Abonnentenzugriffsdienste verwendet werden, mit Microsoft PowerShell erstellt werden. Diese Objekte werden mit den **CsExUmContact** -Cmdlets erstellt und verwaltet.<br/> |
| [Get-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849633) <br/> <br/>[GRANT-CSHostedVoicemailPolicy](https://go.microsoft.com/fwlink/p/?linkid=849602) <br/>                                                                                                                                                | Verwaltet in der Organisation verwendete Richtlinien für gehostete Voicemails. Richtlinien für gehostete Voicemails legen fest, wie nicht angenommene Anrufe an den Exchange UM-Dienst weitergeleitet werden. Diese Richtlinien wirken sich nur auf Benutzer aus, die für gehostete Voicemails in Exchange UM aktiviert sind.  <br/><br/> Um zu überprüfen, ob ein Benutzer für gehostete Voicemails aktiviert ist, führen Sie an der PowerShell-Eingabeaufforderung etwa den folgenden Befehl aus.  <br/> \`Get-CsOnlineUser-Identity "kenmyer@litwareinc.com"                                                                                                                                                                                                                                                                                                                                                           |

## <a name="related-topics"></a>Verwandte Themen
[Einrichten des Computers für Skype für das Business online Management mithilfe von Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 