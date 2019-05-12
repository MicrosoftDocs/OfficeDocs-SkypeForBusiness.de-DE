---
title: Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: öffentlichen instant messaging-Diensten kann Benutzer in Ihrer Organisation Sofortnachrichten verwenden, um die Kommunikation mit Benutzern von Instant Messaging-Diensten von öffentlichen IM-Dienstanbieter bereitgestellt wird.
ms.openlocfilehash: 6cccef5de36b733e1af13092137bf0a35e843b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920439"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Skype für Business Server

Öffentlichen instant messaging (IM)-Diensten kann Benutzer in Ihrer Organisation Sofortnachrichten verwenden, um die Kommunikation mit Benutzern von Instant Messaging-Diensten von öffentlichen IM-Dienstanbieter bereitgestellt wird. Konfigurieren Sie einen oder mehrere externe Benutzer Zugriffsrichtlinien zur Steuerung können, ob mit internen Skype für Business Server-Benutzer mit Benutzern öffentliche zusammenarbeiten können. Öffentliche instant messaging-Diensten ist eine zusätzliche Funktion, die Konfiguration Ihrer Bereitstellung und Benutzern verwendet. Es hängt die Bereitstellung des Diensts auf den öffentlichen IM-Dienstanbieter. 

Um den Zugriff durch öffentliche Benutzer zu kontrollieren, können Sie Richtlinien auf globaler, Standort- und Benutzerebene konfigurieren. Skype für Business Server aufgeführt, die auf einer Richtlinienebene angewendet werden kann Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Skype für Business Server RichtlinienPrioritäten ist: Benutzerrichtlinie (die meisten beeinflussen) überschreibt eine Standortrichtlinie, und klicken Sie dann eine Standortrichtlinie überschreibt eine globale Richtlinie (mindestens beeinflussen). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

Im Fall von Sofortnachrichten-Einladungen hängt die Antwort von der Clientsoftware ab. Die Anforderung wird akzeptiert, sofern externe Absender nicht ausdrücklich durch eine Regel (d. h., die Einstellungen in der Client des Benutzers **Zulassen** und **Sperrlisten** ) blockiert werden. Darüber hinaus können Sofortnachrichten-Einladungen blockiert werden, wenn ein Benutzer wählt alle Sofortnachrichten von Benutzern zu blockieren, die nicht in der **Zulassungsliste** enthalten sind.



> [!NOTE]  
> Sie können Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs konfigurieren, auch wenn Sie nicht den Verbund für Ihre Organisation aktiviert haben. Die Richtlinien, die Sie konfigurieren, werden jedoch in Kraft nur, wenn Sie den Verbund für Ihre Organisation aktiviert sein. Ausführliche Informationen zur Aktivierung des Verbunds finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md). Wenn Sie eine Benutzerrichtlinie zur Steuerung des öffentlichen Benutzerzugriffs angeben, gilt die Richtlinie darüber hinaus nur für Benutzer, die für Skype für Business Server aktiviert und so konfiguriert, dass die Richtlinie verwenden. Ausführliche Informationen zum Angeben von öffentlicher Benutzern, die sich bei Skype für Business Server anmelden können, finden Sie unter [Zuweisen eine Richtlinie für den externen Benutzerzugriff](assign-an-external-user-access-policy.md).


Verwenden Sie das folgende Verfahren, um eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer, der einen oder mehrere öffentliche IM-Dienstanbieter zu konfigurieren.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>So konfigurieren Sie eine externe Zugriffsrichtlinie zur Unterstützung des öffentlichen Benutzerzugriffs

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**und klicken Sie dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** eine der folgenden Aktionen aus:
    
      - Um die globale Richtlinie zur Unterstützung der Zugriff durch öffentliche Benutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
      - Erstellen einer neuen Standortrichtlinie, klicken Sie auf **neu**, und klicken Sie dann auf **Standortrichtlinie**. Klicken Sie im **Dialogfeld Standort auswählen**auf den geeigneten Standort aus der Liste aus, und klicken Sie dann auf **OK**.
    
      - Um eine neue Richtlinie zu erstellen, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzerrichtlinie**. Erstellen Sie in **Neue Richtlinie für den externen Zugriff**einen eindeutigen Namen im Feld **Name** , das angibt, welche Benutzer Richtlinie Hintergrund (beispielsweise **EnablePublicUsers** für eine Benutzerrichtlinie, mit dem öffentlichen Benutzern können).
    
      - Um eine vorhandene Richtlinie zu ändern, klicken Sie auf die entsprechende Richtlinie in der Tabelle, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.

5.  (Optional) Wenn Sie hinzufügen oder bearbeiten eine Beschreibung möchten, geben Sie die Informationen für die Richtlinie im Feld **Beschreibung**.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Um öffentliche Benutzerzugriff für die Richtlinie zu aktivieren, aktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** .
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit öffentlichen Benutzern aktivieren** , um öffentlichen Benutzerzugriffs für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit ausführen**.

Um den Zugriff durch öffentliche Benutzer zu aktivieren, müssen Sie auch Unterstützung für den Verbund in Ihrer Organisation aktivieren. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Benutzerzugriffs in Skype für Business Server federated](configure-policies-to-control-federated-user-access.md).

Ist dies eine Benutzerrichtlinie, müssen Sie auch die Richtlinie mit Benutzern öffentlicher anwenden, die für die Zusammenarbeit mit Benutzern öffentlicher enthalten sein sollen. 


## <a name="see-also"></a>Siehe auch

[Verwalten von SIP-Partnerverbundanbietern für eine Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
