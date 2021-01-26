---
title: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine Konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese Konferenzrichtlinie auf bestimmte Benutzer anwenden.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817455"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Skype for Business Server 


Standardmäßig werden alle Benutzer daran gehindert, anonyme Benutzer zur Teilnahme an einer Besprechung einzuladen. Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine Konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese Konferenzrichtlinie auf bestimmte Benutzer anwenden. Weitere Informationen zum Konfigurieren einer Konferenzrichtlinien zur Unterstützung anonymer Benutzer finden Sie unter "Erstellen von Konferenzrichtlinien [in Skype for Business Server](../../conferencing/create-policies.md) und Verwalten des Verbunds und des externen Zugriffs auf Skype for Business [Server".](../managing-federation-and-external-access.md)

Verwenden Sie das Verfahren in diesem Abschnitt, um eine bereits erstellte Konferenzrichtlinie auf einen oder mehrere Benutzer oder Benutzergruppen anzuwenden.

> [!NOTE]  
> Neben der Konfiguration und Anwendung einer Richtlinie müssen Sie außerdem die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren, um Benutzern das Einladen anonymer Benutzer zu ermöglichen. Weitere Informationen finden Sie unter ["Konfigurieren von Richtlinien zum Steuern des Zugriffs durch öffentliche Benutzer in Skype for Business Server".](../external-access-policies/configure-policies-to-control-public-user-access.md)


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen**, und führen Sie einen der folgenden Schritte aus:
    
    1.  Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableAnonymous** für eine Benutzerrichtlinie, welche die Kommunikation mit anonymen Benutzern aktiviert).
    
    2.  Klicken Sie zum Konfigurieren einer vorhandenen Benutzerrichtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

4.  Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen **Teilnehmern das Einladen anonymer Benutzer gestatten**.

5.  Klicken Sie auf **Commit**.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und suchen Sie anschließend nach dem Benutzerkonto, das Sie konfigurieren möchten.

7.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

8.  Wählen Sie im Bereich **"Skype for Business Server-Benutzer** bearbeiten" unter "Konferenzrichtlinie" die Benutzerrichtlinie mit der Konfiguration für anonymen Benutzerzugriff **aus,** die Sie auf diesen Benutzer anwenden möchten.  

    > [!NOTE]  
    > Die <STRONG> &lt; automatischen &gt; </STRONG> Einstellungen übernehmen die Standardeinstellungen für die Serverinstallation und werden automatisch vom Server angewendet.


Damit Benutzer anonyme Benutzer zu Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren. Weitere Informationen finden Sie unter ["Konfigurieren von Richtlinien zum Steuern des Zugriffs durch öffentliche Benutzer in Skype for Business Server".](../external-access-policies/configure-policies-to-control-public-user-access.md)

