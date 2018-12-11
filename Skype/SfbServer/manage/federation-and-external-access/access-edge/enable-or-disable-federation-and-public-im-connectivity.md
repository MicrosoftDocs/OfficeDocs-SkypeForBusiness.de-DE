---
title: Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Unterstützung für den Verbund erforderlich ist, um Benutzern zu ermöglichen, die über ein Konto mit einer vertrauenswürdigen Kunden oder Partner Organisation, einschließlich Partnerdomänen und Benutzer des öffentlichen instant messaging (IM)-Anbieter-Benutzer, die Sie Unterstützung für die Zusammenarbeit mit Benutzern in Ihrer Organisation.
ms.openlocfilehash: 9e293c70565832944a10e3c6d2533425c747197e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222996"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>Aktivieren Sie oder deaktivieren Sie den Verbund und öffentliches Instant Messaging-Diensten in Skype für Business Server

Unterstützung für den Verbund erforderlich ist, um Benutzern zu ermöglichen, die über ein Konto mit einer vertrauenswürdigen Kunden oder Partner Organisation, einschließlich Partnerdomänen und Benutzer des öffentlichen instant messaging (IM)-Anbieter-Benutzer, die Sie Unterstützung für die Zusammenarbeit mit Benutzern in Ihrer Organisation. Verbund ist auch erforderlich, auf einen gehosteten Exchange-Dienstanbieter zu verwenden, um Voicemail für Enterprise-VoIP-Benutzer bereitzustellen, deren Postfächer über einen gehosteten Exchange-Dienst wie beispielsweise Microsoft Exchange Online verwaltet werden. Wenn Sie eine Vertrauensstellung mit dieser externen Domänen eingerichtet haben, können Sie Autorisieren von Benutzern in diesen Domänen den Zugriff auf Ihre Bereitstellung und Skype für Business Serverkommunikation teilnehmen. Diese Vertrauensstellung ein Verbund aufgerufen, und es wird kein Zusammenhang, oder in Abhängigkeit von einem Active Directory-Vertrauensstellung.

Um den Zugriff durch Benutzer von Partnerdomänen zu unterstützen, müssen Sie den Verbund aktivieren. Wenn Sie den Verbund für Ihre Organisation aktivieren, müssen Sie auch angeben, ob implementieren Sie die folgenden Optionen:

  - **Aktivieren Sie Partner Domäne Discovery**   Wenn Sie diese Option aktivieren, verwendet Skype für Business Server Domain Name System (DNS) Datensätze versuchen ermitteln können nicht in der Liste zugelassener Domänen aufgeführt ermittelt automatisch Auswertung von eingehenden Datenverkehr von Domänen Verbund-Partner und eingeschränkt oder Blockierung dieser Datenverkehr basierend auf Vertrauensebene, Umfang des Datenverkehrs und administratoreinstellungen. Wenn Sie diese Option nicht auswählen, wird partnerbenutzerzugriff für Benutzer in den Domänen nur aktiviert, die Sie in der Liste der zugelassenen Domänen hinzufügen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass diese Person Domänen blockiert oder zulässig, einschließlich Einschränken des Zugriffs auf bestimmten Servern in der Partnerdomäne Zugriffs-edgedienst ausgeführt. Ausführliche Informationen zum Steuern des Zugriffs aus Partnerdomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).

  - **Senden ein Archivierungshaftungsausschlusses an Verbundpartner**     Haftungsausschluss mitgeteilt wird an Verbundpartner, die Archivierung in Ihrer Bereitstellung vorhanden ist. Wenn Sie die Archivierung der externen Kommunikation mit verbundpartnerdomänen unterstützen, sollten Sie den Archivierungshaftungsausschluss für Partner zu warnen, wenn deren Nachrichten archiviert werden aktivieren.

Wenn Sie später vorübergehend oder endgültig des Zugriffs durch Benutzer von Partnerdomänen zu verhindern möchten, können Sie den Verbund für Ihre Organisation deaktivieren. Verwenden Sie das Verfahren in diesem Abschnitt zum Aktivieren oder Deaktivieren von partnerbenutzerzugriff für Ihre Organisation, einschließlich der Angabe der entsprechenden Verbund-Optionen für Ihre Organisation unterstützt werden müssen.

> [!NOTE]  
> Aktivierung des Verbunds für Ihre Organisation gibt nur an, dass Ihre Server mit Zugriffs-edgediensts unterstützen routing an Partnerdomänen. Benutzer in verbunddomänen können nicht in Sofortnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie zur Unterstützung der partnerbenutzerzugriff konfigurieren. Benutzer öffentlicher IM-Dienstanbieter können nicht in Sofortnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie mindestens eine Richtlinie zur Unterstützung der öffentlichen Instant Messaging-Diensten auch konfigurieren. Skype für Business Server kann erst verwenden, einen gehosteten Exchange-Dienst um Anrufbeantwortung, Outlook Voice Access (einschließlich Voicemail), bereitzustellen oder automatische Telefonzentrale für Benutzer, deren Postfächer, über einen gehosteten Exchange-Dienst konfigurieren Sie eine gehostete Voicemail e-Mail-Richtlinie, die Routinginformationen bereitstellt. Ausführliche Informationen zum Konfigurieren von Richtlinien für die Kommunikation mit Benutzern von Partnerdomänen in anderen Organisationen finden Sie unter [Verwalten von SIP-verbunddomänen für Ihre Organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md). Darüber hinaus, wenn Sie die Kommunikation mit Benutzern IM-Dienstanbieter unterstützen möchten, müssen Sie Richtlinien konfigurieren, um ihn unterstützen, und auch Konfigurieren der Unterstützung für die einzelnen-Dienstanbieter, die Sie unterstützen möchten. Weitere Informationen hierzu finden Sie unter [Verwalten von SIP-verbundanbietern für Ihre Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>So aktivieren oder Deaktivieren von partnerbenutzerzugriff für Ihre Organisation

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**und klicken Sie dann auf **Konfiguration für Zugriffsedge**.

4.  Klicken Sie auf der Seite **Konfiguration für Zugriffsedge** auf **Global**, klicken Sie auf **Bearbeiten**und klicken Sie dann auf **Details anzeigen**.

5.  Führen Sie in der **Konfiguration für Zugriffsedge bearbeiten**eine der folgenden Aktionen aus:
    
      - Um den partnerbenutzerzugriff für Ihre Organisation zu aktivieren, aktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** .
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** , um den partnerbenutzerzugriff für Ihre Organisation zu deaktivieren.

6.  Wenn Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren** ausgewählt haben, führen Sie folgende Schritte aus:
    
    1.  Wenn Sie die automatische Suche von Partnerdomänen zu unterstützen möchten, aktivieren Sie das Kontrollkästchen **Partner Domäne Discovery aktivieren** .
    
    2.  Wenn Ihre Organisation die Archivierung der externen Kommunikation unterstützt, aktivieren Sie das Kontrollkästchen **Archivierungshaftungsausschluss an Verbundpartner senden** .

7.  Klicken Sie auf **Commit ausführen**.

Um Verbundbenutzer Zusammenarbeit mit Benutzern in Ihrer Skype für Business Server-Bereitstellung zu aktivieren, müssen Sie auch mindestens eine externe Zugriffsrichtlinie zur Unterstützung der partnerbenutzerzugriff konfigurieren. Weitere Informationen hierzu finden Sie unter [Konfigurieren von Richtlinien zur Steuerung federated User Access](../external-access-policies/configure-policies-to-control-federated-user-access.md). Zur Steuerung des Zugriffs für spezifische Partnerdomänen finden Sie unter [Konfigurieren der Unterstützung für zulässige externe Domänen](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren der Verbund und Verbindung mit öffentlichen Sofortnachrichtendiensten mithilfe von Windows PowerShell-cmdlets

Verbund und öffentliches Instant Messaging-Diensten können auch mithilfe von Windows PowerShell und das Set-CsAccessEdgeConfiguration-Cmdlet verwaltet werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>So aktivieren Sie den Verbund und öffentliches Instant Messaging-Diensten

  - Um den Verbund und Verbindung mit öffentlichen Sofortnachrichtendiensten zu aktivieren, legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "true" ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>So deaktivieren Sie den Verbund und öffentliches Instant Messaging-Diensten

  - Um den Verbund und Verbindung mit öffentlichen Sofortnachrichtendiensten zu deaktivieren, legen Sie den Wert der Eigenschaft **AllowFederatedUsers** auf "false" ($False):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

