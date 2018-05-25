---
title: Anfordern, Installieren oder Zuweisen von Zertifikaten
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: 'Schritt 3: Zertifikate anfordern, installieren oder zuweisen startet den Zertifikat-Assistenten beim Klicken auf ausführen. Die Zertifikate, die mit dem Assistenten konfiguriert sind basieren auf die Definition der Skype für Business Server 2015 Topologie, die konfiguriert und in den zentralen Verwaltungsspeicher von Topology Builder veröffentlicht wird. Damit der Zertifikat-Assistent für eine Onlinezertifizierungsstelle in Ihrer Organisation erfolgreich ausgeführt werden kann, müssen Sie am Computer als Mitglied der lokalen Gruppe „Administratoren“ angemeldet sein. Ferner müssen Sie ein authentifizierter Domänenbenutzer in der Domäne des Computers und der Zertifizierungsstelle sein. Klicken Sie im Assistenten bietet die Möglichkeit, alternativen Anmeldeinformationen für den Zugriff eines Unternehmens-CA anzugeben.'
ms.openlocfilehash: 356983659e409673f98a984f767ec5ac5127845a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2018
---
# <a name="request-install-or-assign-certificates"></a>Anfordern, Installieren oder Zuweisen von Zertifikaten
 
 In **Schritt 3: Anfordern, Installieren und Zuweisen von Zertifikaten** wird beim Klicken auf **Ausführen** der Zertifikat-Assistent gestartet. Die Zertifikate, die mit dem Assistenten konfiguriert sind basieren auf die Definition der Skype für Business Server 2015 Topologie, die konfiguriert und in den zentralen Verwaltungsspeicher von Topology Builder veröffentlicht wird. Damit der Zertifikat-Assistent für eine Onlinezertifizierungsstelle in Ihrer Organisation erfolgreich ausgeführt werden kann, müssen Sie am Computer als Mitglied der lokalen Gruppe „Administratoren“ angemeldet sein. Ferner müssen Sie ein authentifizierter Domänenbenutzer in der Domäne des Computers und der Zertifizierungsstelle sein. Klicken Sie im Assistenten bietet die Möglichkeit, alternativen Anmeldeinformationen für den Zugriff eines Unternehmens-CA anzugeben.
  
> [!NOTE]
> Sie können mithilfe des Zertifikat-Assistenten auch Offlinezertifikatsanforderungen erstellen und verarbeiten, die an eine öffentliche Zertifizierungsstelle oder eine andere Offline-PKI (Public Key-Infrastruktur) gesendet werden. Zum Erstellen einer Offlineanforderung sind nur die üblichen Berechtigungen für die Anmeldung am Computer erforderlich. Zum Verarbeiten der Antwort der öffentlichen Zertifizierungsstelle und zum Zuweisen des Zertifikats zum jeweiligen Computer bzw. zur jeweiligen Rolle müssen Sie als Mitglied der lokalen Gruppe „Administratoren“ (oder einer ähnlichen Gruppe) angemeldet sein. 
  

