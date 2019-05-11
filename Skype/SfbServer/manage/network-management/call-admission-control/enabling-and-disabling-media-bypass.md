---
title: Aktivieren und Deaktivieren der medienumgehung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Verwenden Sie die Verfahren in diesem Artikel zum Aktivieren oder deaktivieren die medienumgehung mithilfe der Skype für Business Server-Systemsteuerung.
ms.openlocfilehash: 57d0c601775861d948c950db4b429aca4d988da7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888436"
---
# <a name="enabling-and-disabling-media-bypass-in-skype-for-business-server"></a>Aktivieren und Deaktivieren der Medienumgehung in Skype for Business Server

Verwenden Sie die Verfahren in diesem Artikel zum Aktivieren oder deaktivieren die medienumgehung mithilfe der Skype für Business Server-Systemsteuerung.

## <a name="enable-network-media-bypass"></a>Aktivieren der netzwerkmedienumgehung 

Einstellungen für die medienumgehung gelten global für einen Skype für Business Server-Bereitstellung. Die medienumgehung lässt Aufrufe Umgehung des Vermittlungsservers. Ausführliche Informationen zur Verwendung von Medien zu umgehen, finden Sie unter [Plan für Medien zu umgehen](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

Sie können aktivieren und Konfigurieren der medienumgehung aus der Skype Business Server-Systemsteuerung.


### <a name="to-enable-and-configure-media-bypass"></a>Zum Aktivieren und Konfigurieren der medienumgehung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global** . Es ist immer nur eine Konfiguration, und es heißt immer Global.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Klicken Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **medienumgehung aktivieren** .

7.  Wählen Sie eine der folgenden Optionen aus:
    
      - **Immer umgehen**   wählen Sie diese Option, um Medien versuchen für alle Anrufe zu umgehen. Diese Option wird nicht verfügbar, wenn die anrufsteuerung (CAC) aktiviert ist. Wenn CAC nicht aktiviert ist, wählen Sie diese Option in den folgenden Situationen:
        
          - Besteht keine Notwendigkeit zur bandbreitensteuerung.
        
          - Es besteht keine Notwendigkeit abgestimmte Konfiguration, um zu bestimmen, wann Umgehung geschehen soll.
        
          - Es ist vollständige Konnektivität zwischen Gateways und Clients.
    
      - **Verwenden Sie Standorte und Regionen**   wenn CAC aktiviert ist, diese Option ist standardmäßig aktiviert und kann nicht geändert werden. Wenn diese Option ausgewählt ist, werden netzwerkkonfigurationsstandorte und Regionen verwendet werden, um zu bestimmen, wann die medienumgehung möglich ist. Wenn Sie diese Option auswählen, können Sie auswählen, um Umgehung für Websites zu aktivieren, die nicht zugeordnet werden. Klicken Sie auf das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren** nur, wenn Sie verfügen über eine oder mehrere große Standorte derselben Region zugeordnet, die keine bandbreiteneinschränkungen (beispielsweise einem großen zentralen Standort) und Ihnen auch einige Zweigniederlassungen zugeordnet die derselben Region, die bandbreiteneinschränkungen aufweisen. Wenn Sie aktivieren für nicht zugeordnete Standorte umgehen, Konfiguration wird optimiert, da Sie nur die die Zweigniederlassungen zugeordnete Subnetze angeben, statt dass alle Subnetze angeben müssen alle Websites zugeordnet. Es wird empfohlen, dass Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren** nicht auswählen, wenn die Anrufsteuerung aktiviert ist.

8.  Klicken Sie auf **Commit** , um die Änderungen zu speichern.


## <a name="disable-network-media-bypass"></a>Deaktivieren der netzwerkmedienumgehung

Einstellungen für die medienumgehung gelten global für einen Skype für Business Server-Bereitstellung. Die medienumgehung lässt Aufrufe Umgehung des Vermittlungsservers. Ausführliche Informationen zur Verwendung von Medien zu umgehen, finden Sie unter [Plan für Medien zu umgehen](../../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). Sie können die medienumgehung über die Skype Business Server-Systemsteuerung deaktivieren. 


### <a name="to-disable-media-bypass"></a>So deaktivieren Sie die medienumgehung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global** . Es ist immer nur eine Konfiguration, und es heißt immer Global.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Deaktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **medienumgehung aktivieren** .

7.  Klicken Sie auf **Commit** , um die Änderungen zu speichern.

  
