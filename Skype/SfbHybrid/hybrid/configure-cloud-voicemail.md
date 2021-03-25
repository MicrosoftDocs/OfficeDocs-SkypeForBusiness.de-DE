---
title: Konfigurieren des Cloud-Voicemaildiensts für lokale Benutzer
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Anweisungen zum Implementieren cloudbasierter Voicemail für Benutzer, die in Skype for Business Server gespeichert sind.
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118984"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Konfigurieren des Cloud-Voicemaildiensts für lokale Benutzer

## <a name="overview"></a>Übersicht 
In diesem Artikel wird beschrieben, wie Sie den Microsoft Cloud Voicemaildienst für Ihre lokalen Skype for Business-Benutzer konfigurieren.  

In diesem Artikel wird davon ausgegangen, dass Skype for Business Server bereits in einer unterstützten Topologie bereitgestellt ist und dass Sie die Voraussetzungen für das Einrichten der Hybridkonnektivität erfüllt haben.

Weitere Informationen zu den Vorteilen, Planungsüberlegungen und Anforderungen für die Implementierung von Cloud Voicemail finden Sie unter [Plan Cloud Voicemail service](plan-cloud-voicemail.md).




Das Konfigurieren von Cloud Voicemail umfasst die folgenden Aufgaben:

1.  Stellen Sie sicher, dass Sie die voraussetzungen erfüllt haben, wie unter [Plan Cloud Voicemail service beschrieben.](plan-cloud-voicemail.md)

2.  Stellen Sie sicher, dass Sie die Hybridkonnektivität wie unter [Planen](plan-hybrid-connectivity.md) der Hybridkonnektivität und [Konfigurieren der Hybridkonnektivität beschrieben eingerichtet haben.](configure-hybrid-connectivity.md) 

3.  [Konfigurieren Sie Cloud Voicemail als Hostinganbieter auf dem Front-End-Server,](#configure-cloud-voicemail-as-the-hosting-provider) wie in diesem Artikel beschrieben.

4.  [Konfigurieren Sie eine gehostete Voicemailrichtlinie,](#configure-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben.

5.  [Weisen Sie eine gehostete Voicemailrichtlinie zu,](#assign-a-hosted-voicemail-policy) wie in diesem Artikel beschrieben.

6.  [Aktivieren Sie einen Benutzer für Cloud Voicemail,](#enable-a-user-for-cloud-voicemail) wie in diesem Artikel beschrieben.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Konfigurieren von Cloud Voicemail als Hostinganbieter 

Sie konfigurieren Cloud Voicemail als Hostinganbieter auf einem Front-End-Server, indem Sie das cmdlet New-CsHostingProvider mit den folgenden Parametern verwenden:

- **Identity** gibt einen eindeutigen Zeichenfolgenwertbezeichner für den Hostinganbieter an, den Sie erstellen. z. B. Cloud Voicemail. 

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf True festgelegt werden.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf True festgelegt werden.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype for Business Server-Konten verwendet wird. Dieser Parameter muss auf False festgelegt werden.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den vom Hostinganbieter verwendeten Proxyserver an. Beispiel: proxyserver.contoso.com. Sie erhalten diese Information von Ihrem Hostinganbieter. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, müssen Sie den Eintrag für diesen Anbieter löschen und dann neu erstellen.

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype for Business Server-Topologie enthalten ist. Dieser Parameter muss auf False festgelegt werden.

In der Skype for Business Management-Shell konfiguriert das folgende Cmdlet beispielsweise Cloud Voicemail als Hostinganbieter:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Konfigurieren einer gehosteten Voicemailrichtlinie

Um sicherzustellen, dass Voicemail für Ihre Organisation an den Cloud-Voicemaildienst geroutet wird, müssen Sie eine gehostete Voicemailrichtlinie für Ihre Organisation konfigurieren. In vielen Fällen ist nur eine gehostete Voicemailrichtlinie erforderlich, und Sie können die globale Richtlinie so ändern, dass alle Ihre Anforderungen erfüllt werden. Wenn Ihre Organisation mehrere gehostete Voicemailrichtlinien erfordert, können Sie Richtlinien mithilfe des cmdlets new-cshostedvoicemailpolicy hinzufügen.

Führen Sie zum Ändern der globalen Richtlinie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell aus, nachdem Sie Ihre Organisation und Mandanten-ID aktualisiert haben:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des gehosteten Cloud Voicemaildiensts an. Dieser Wert sollte auf **exap.um.outlook.com.**

- **Organization** ist die Standarddomäne, die Ihrem Mandanten zugewiesen ist. Sie können diese Informationen abrufen, indem Sie den Mandantenadministrator bei office.com anmelden, auf die Admin Center-App klicken, links zu **Setup** navigieren und auf **Domänen klicken.** Beispiel: mytenant.onmicrosoft.com.

    Der Organisationsname ist auch der Standarddomänenname in Microsoft 365 oder Office 365.

Führen Sie den folgenden Befehl aus, um sicherzustellen, dass eine gehostete Voicemailrichtlinie erfolgreich erstellt wurde:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Zuweisen einer gehosteten Voicemailrichtlinie

Standardmäßig wird die global gehostete Voicemailrichtlinie allen Benutzern zugewiesen. Wenn Sie eine andere Richtlinie verwenden, müssen Sie benutzern vor der Aktivierung der gehosteten Voicemail zunächst die gewünschte gehostete Voicemailrichtlinie mithilfe des [Grant-CSHostedVoicemailPolicy-Cmdlets](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) erteilen.

Der folgende Befehl weist beispielsweise einem Benutzer eine nicht global gehostete Voicemailrichtlinie zu:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Aktivieren eines Benutzers für Cloud Voicemail

Verwenden Sie das [Cmdlet Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) mit dem Parameter HostedVoiceMail, um die Route der Voicemailanrufe eines Benutzers an Cloud Voicemail zu ermöglichen. 

Mit dem folgenden Befehl wird beispielsweise ein Benutzerkonto für Cloud Voicemail aktiviert: 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

Das Cmdlet überprüft, ob eine Cloud Voicemailrichtlinie auf globaler, Standort- oder Benutzerebene für diesen Benutzer gilt. Wenn keine Richtlinie gilt, schlägt das Cmdlet fehl.  

Im nächsten Beispiel wird ein Benutzerkonto für Cloud Voicemail deaktiviert:

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

Das Cmdlet überprüft, ob keine gehostete Voicemailrichtlinie auf globaler, Standort- oder Benutzerebene für diesen Benutzer gilt. Wenn eine Richtlinie angewendet wird, schlägt das Cmdlet fehl.

> [!NOTE]
>  Benutzer müssen für die Verwendung des Microsoft Cloud Voicemail Service unternehmensfähig sein.