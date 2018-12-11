---
title: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie steuern, wer anonyme Benutzer einladen kann durch Konfigurieren einer konferenzrichtlinie so, dass anonyme Benutzer unterstützen und diese konferenzrichtlinie auf bestimmte Benutzer anwenden.
ms.openlocfilehash: 5d3ade88a9d4ca0f639d7119da53f8180af6c30d
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222730"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Zuweisen von konferenzrichtlinien zur Unterstützung anonymer Benutzer in Skype für Business Server 


Standardmäßig werden alle Benutzer daran gehindert anonyme Benutzer zur Teilnahme an einer Besprechung einladen. Sie steuern, wer anonyme Benutzer einladen kann durch Konfigurieren einer konferenzrichtlinie so, dass anonyme Benutzer unterstützen und diese konferenzrichtlinie auf bestimmte Benutzer anwenden. Ausführliche Informationen zum Konfigurieren einer konferenzrichtlinien zur Unterstützung der anonyme Benutzer finden Sie unter [konferenzrichtlinien in Skype für Business Server erstellen](../../conferencing/create-policies.md) und [Verwalten von Verbund und externen Zugriff auf Skype für Business Server](../managing-federation-and-external-access.md).

Verwenden Sie das Verfahren in diesem Abschnitt, um einen oder mehrere Benutzer oder Benutzergruppen zuweisen eine konferenzrichtlinie, die Sie bereits erstellt haben.

> [!NOTE]  
> Zusätzlich zu konfigurieren und Anwenden einer Richtlinie, um Benutzer können anonyme Benutzer einladen zu aktivieren, müssen Sie auch die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Skype für Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  In der linken Navigationsleiste auf **Konferenzen**und führen Sie dann eine der folgenden:
    
    1.  Um eine neue Richtlinie zu erstellen, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie einen eindeutigen Namen im Feld **Name** , das angibt, welche die Benutzerrichtlinie (beispielsweise **EnableAnonymous** für eine Benutzerrichtlinie, die die Kommunikation mit anonymen Benutzern ermöglicht) behandelt.
    
    2.  Um eine vorhandene Benutzerrichtlinie zu konfigurieren, klicken Sie auf die entsprechende Richtlinie in der Tabelle, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

4.  Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen **anonyme Benutzer einladen von Teilnehmern gestatten** .

5.  Klicken Sie auf **Commit ausführen**.

6.  In der linken Navigationsleiste auf **Benutzer**, und suchen Sie auf das Benutzerkonto, das Sie konfigurieren möchten.

7.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

8.  **Skype für Business Server-Benutzer bearbeiten** unter **konferenzrichtlinie**wählen Sie die Benutzerrichtlinie mit der Konfiguration des Zugriffs anonymer Benutzer, die Sie für diesen Benutzer anwenden möchten.  

    > [!NOTE]  
    > Die <STRONG> &lt;automatische&gt; </STRONG> Einstellungen gelten die Standardeinstellungen für Server-Installation und werden vom Server automatisch angewendet.


Damit Benutzer können anonyme Benutzer auf Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Skype für Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

