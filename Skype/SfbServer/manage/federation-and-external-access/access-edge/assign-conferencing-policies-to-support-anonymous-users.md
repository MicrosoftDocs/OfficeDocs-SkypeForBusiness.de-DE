---
title: Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese konferenzrichtlinie auf bestimmte Benutzer anwenden.
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280285"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Skype for Business Server 


Standardmäßig werden alle Benutzer daran gehindert, anonyme Benutzer zur Teilnahme an einer Besprechung einzuladen. Sie steuern, wer anonyme Benutzer einladen kann, indem Sie eine konferenzrichtlinie für die Unterstützung anonymer Benutzer konfigurieren und diese konferenzrichtlinie auf bestimmte Benutzer anwenden. Details zum Konfigurieren von Konferenzrichtlinien zur Unterstützung anonymer Benutzer finden Sie unter [Erstellen von Konferenzrichtlinien in Skype for Business Server](../../conferencing/create-policies.md) und [Verwalten des Föderations-und externen Zugriffs auf Skype for Business Server](../managing-federation-and-external-access.md).

Verwenden Sie das Verfahren in diesem Abschnitt, um eine konferenzrichtlinie anzuwenden, die Sie bereits für einen oder mehrere Benutzer oder Benutzergruppen erstellt haben.

> [!NOTE]  
> Neben der Konfiguration und Anwendung einer Richtlinie, mit der Benutzer anonyme Benutzer einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer für Ihre Organisation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von öffentlichen Benutzern in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>So konfigurieren Sie eine Benutzerrichtlinie für die anonyme Teilnahme an Besprechungen

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenzen**, und führen Sie dann eine der folgenden Aktionen aus:
    
    1.  Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie im Feld **Name** einen eindeutigen Namen, der angibt, was die Benutzerrichtlinie umfasst (beispielsweise **EnableAnonymous** für eine Benutzerrichtlinie, die die Kommunikation mit anonymen Benutzern ermöglicht).
    
    2.  Wenn Sie eine vorhandene Benutzerrichtlinie konfigurieren möchten, klicken Sie auf die entsprechende Richtlinie, die in der Tabelle aufgeführt ist, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

4.  Aktivieren Sie im Dialogfeld **Konferenzrichtlinien** das Kontrollkästchen Teilnehmern die Möglichkeit geben, **anonyme Benutzer einzuladen** .

5.  Klicken Sie auf **Commit ausführen**.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, suchen Sie nach dem Benutzerkonto, das Sie konfigurieren möchten.

7.  Klicken Sie in der Tabelle mit den Suchergebnissen auf das Benutzerkonto, klicken Sie auf **Bearbeiten** und dann auf **Details anzeigen**.

8.  Wählen Sie in **Skype for Business Server-Benutzer bearbeiten** unter **konferenzrichtlinie**die Benutzerrichtlinie mit der Konfiguration für den anonymen Benutzer Zugriff aus, die Sie auf diesen Benutzer anwenden möchten.  

    > [!NOTE]  
    > Die <STRONG> &lt;automatischen&gt; </STRONG> Einstellungen wenden die Standardeinstellungen für Server Installationen an und werden automatisch vom Server angewendet.


Damit Benutzer anonyme Benutzer zu Konferenzen einladen können, müssen Sie auch die Unterstützung für anonyme Benutzer in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von öffentlichen Benutzern in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

