---
title: Vorbereiten von Active Directory
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Um mit der Installation von Skype for Business Server 2015 zu beginnen, müssen Sie das Active Directory Domain Services-Schema, die Gesamtstruktur und die Domänen vorbereiten, die Server und Benutzer hosten. Der Skype for Business Server-Bereitstellungs-Assistent führt Sie durch die schritte, die zum Vorbereiten von Active Directory erforderlich sind, beginnend mit dem Schema und dann in die Gesamtstrukturvorbereitung. Nachdem Sie bestätigt haben, dass die Active Directory-Replikation erfolgreich ist, bereiten Sie dann jede Domäne vor, die Benutzer oder Server hosten wird.
ms.openlocfilehash: 3a83f41846a5795670b07ce17330dbd5b2bfde29
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770863"
---
# <a name="prepare-active-directory"></a>Vorbereitung von Active Directory

Um mit der Installation von Skype for Business Server 2015 zu beginnen, müssen Sie das Active Directory Domain Services-Schema, die Gesamtstruktur und die Domänen vorbereiten, die Server und Benutzer hosten. Der Skype for Business Server-Bereitstellungs-Assistent führt Sie durch die schritte, die zum Vorbereiten von Active Directory erforderlich sind, beginnend mit dem Schema und dann in die Gesamtstrukturvorbereitung. Nachdem Sie bestätigt haben, dass die Active Directory-Replikation erfolgreich ist, bereiten Sie dann jede Domäne vor, die Benutzer oder Server hosten wird.

> [!IMPORTANT]
> Um das Schema erfolgreich vorbereiten zu können, müssen Sie als Mitglied der Gruppen "Organisations-Admins" und "Schema-Admins" angemeldet sein. Zum Vorbereiten der Gesamtstruktur müssen Sie als Mitglied der Gruppe "Organisations-Admins" oder als Administrator im Gesamtstrukturstamm angemeldet sein. Zur Vorbereitung der Domäne müssen Sie als Mitglied der Gruppe "Domänen-Admins" angemeldet sein.

Ausführliche Informationen zu unterstützten Active Directory-Topologien finden Sie unter [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in der Unterstützungsdokumentation. Ausführliche Informationen zur Active Directory-Vorbereitung finden Sie unter [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in der Bereitstellungsdokumentation.