---
title: Vorbereiten von Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Um mit der Installation von Skype for Business Server zu beginnen, müssen Sie das Active Directory Domain Services-Schema, die Gesamtstruktur und die Domänen vorbereiten, die Server und Benutzer hosten. Der Skype for Business Server-Bereitstellungs-Assistent führt Sie durch die schritte, die zum Vorbereiten von Active Directory erforderlich sind, beginnend mit dem Schema und dann in die Gesamtstrukturvorbereitung. Nachdem Sie bestätigt haben, dass die Active Directory-Replikation erfolgreich ist, bereiten Sie dann jede Domäne vor, die Benutzer oder Server hosten wird.
ms.openlocfilehash: 86c548f59f7f6d3613971ff8765f01f3a4aa68b7965c402e126cdd9b7fa0a0b6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282222"
---
# <a name="prepare-active-directory"></a>Vorbereitung von Active Directory

Um mit der Installation von Skype for Business Server zu beginnen, müssen Sie das Active Directory Domain Services-Schema, die Gesamtstruktur und die Domänen vorbereiten, die Server und Benutzer hosten. Der Skype for Business Server-Bereitstellungs-Assistent führt Sie durch die schritte, die zum Vorbereiten von Active Directory erforderlich sind, beginnend mit dem Schema und dann in die Gesamtstrukturvorbereitung. Nachdem Sie bestätigt haben, dass die Active Directory-Replikation erfolgreich ist, bereiten Sie dann jede Domäne vor, die Benutzer oder Server hosten wird.

> [!IMPORTANT]
> Um das Schema erfolgreich vorbereiten zu können, müssen Sie als Mitglied der Gruppen "Organisations-Admins" und "Schema-Admins" angemeldet sein. Zum Vorbereiten der Gesamtstruktur müssen Sie als Mitglied der Gruppe "Organisations-Admins" oder als Administrator im Gesamtstrukturstamm angemeldet sein. Zur Vorbereitung der Domäne müssen Sie als Mitglied der Gruppe "Domänen-Admins" angemeldet sein.

Ausführliche Informationen zu unterstützten Active Directory-Topologien finden Sie unter [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in der Unterstützungsdokumentation. Ausführliche Informationen zur Active Directory-Vorbereitung finden Sie unter [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in der Bereitstellungsdokumentation.