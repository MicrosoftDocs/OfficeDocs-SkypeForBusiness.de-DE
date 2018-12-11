---
title: Konfigurieren der Unterstützung von Partnerverbund für einen Skype für Business Online-Kunden
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Wenn Sie Skype für Unternehmen in Ihrer Organisation bereitstellen, können Sie für Business Online-Kunden einen Verbund mit der eine oder mehrere Skype-Domänen konfigurieren. '
ms.openlocfilehash: 978da18a4ae639e52dedd6971c1a2291c94cb9f1
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223367"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Konfigurieren von verbundunterstützung für einen Skype für Business Online-Kunden in Skype für Business Server 

Sie können Communications für Benutzer in Ihrer Organisation in einer der folgenden Methoden bereitstellen:

  - Bereitstellen von Skype für Business Server in Ihrer Organisation (bekannt als *Lokale Dienste*) und Einrichten von Skype für Business Benutzerkonten in Ihrer Organisation.
  - Einrichten einer Microsoft Skype für Business Online Kundenkontos bei einem Hostinganbieter und Einrichten von Benutzerkonten beim Hostinganbieter (auch bekannt als *Onlinedienste*).

Wenn Sie Skype für Unternehmen in Ihrer Organisation bereitstellen, können Sie für Business Online-Kunden einen Verbund mit der eine oder mehrere Skype-Domänen konfigurieren. Um den Verbund zwischen Benutzern von Ihrer lokalen Skype für die Business-Bereitstellung und Benutzer von einer Skype für Business Online-Kunden zu aktivieren, müssen Sie die Unterstützung für die Domäne und Benutzer von der Skype für Business Online-Kunden konfigurieren.

> [!NOTE]  
> In dieser Dokumentation beschrieben nur für die Konfiguration Ihrer Organisation für den Verbund mit einer Skype für Business Online-Kunden zu unterstützen. Die Verfahren zum Konfigurieren der Skype für Business Online-Kunden zur Unterstützung des Verbunds beschrieben in dieser Dokumentation nicht. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Erforderliche Komponenten für den Partnerverbund mit einem Skype für Business Online-Kunden

Wenn Sie einen Verbund mit einer Skype für Business Online-Kunden konfigurieren, sollten Sie bereits erstmalige Bereitstellung und Konfiguration von Skype for Business Server in Ihrer Organisation ausgeführt haben. Dazu gehört Folgendes:

  - Bereitstellen von mindestens einem Standard Edition-Server oder einen Enterprise Edition-Front-End-Pool in Ihrer Organisation. 
  - Aktivieren von internen Benutzerkonten für Skype für Business Server. 
  - Bereitstellen von mindestens einem Edge-Server und die anderen Komponenten muss Zugriff durch externe Benutzer unterstützen. Weitere Informationen hierzu finden Sie unter [Managing Federation und externen Zugriff auf Skype für Business Server](../managing-federation-and-external-access.md).
  - Aktivieren der Unterstützung für Identitätsverbund innerhalb Ihrer Organisation und die entsprechende Methode zum Steuern des Zugriffs von Partnerdomänen zu konfigurieren. Weitere Informationen hierzu finden Sie unter [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer](../access-edge/enable-or-disable-remote-user-access.md) und [Verwalten von SIP-verbundanbietern für Ihre Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Aktivieren für Benutzer in Ihrer Organisation den Zugriff externer Benutzer. Weitere Informationen hierzu finden Sie unter [weisen eine Zugriffsrichtlinie externer Benutzer auf einen Skype für Business aktivierten Benutzer](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Konfigurieren der verbundunterstützung für einen Skype für Business Online-Domäne

Einrichten eines partnerverbunds mit einem Skype für Business Online-Kunden müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren der Unterstützung für die Domäne der Skype für Business Online 2010 Customer (beispielsweise contoso.onmicrosoft.com). Wie bei den [erforderlichen Komponenten für den Partnerverbund mit einem Skype für Business Online-Kunden](#prerequisites-for-federating-with-a-skype-for-business-online-customer)angegeben sollten Sie bereits ein Verbund für Ihre Organisation aktiviert haben. Aktivieren der Verbund erfordert angeben der Methode zur Steuerung des Zugriffs von verbunddomänen verwendet werden. Wenn Sie zum Verwenden der Erkennung Ihrer Organisation konfiguriert haben, ist das Hinzufügen der Domäne zu Ihrer Organisation Liste zulässiger optional. Wenn Sie die Domäne Discovery nicht aktiviert haben, müssen Sie den Domänennamen der der Skype für Business Online-Kunden zu Ihrer Liste der zugelassenen Domänen hinzufügen. Sie können einen Domänennamen mit Skype für Business Server-Systemsteuerung oder durch Ausführen des Cmdlets **New-CSAllowedDomain** hinzufügen. Ausführliche Informationen zur Verwendung von Skype Business Server-Systemsteuerung, einschließlich der Aktivierung der Ermittlung von Domänen finden Sie unter [Verwalten von SIP-verbundanbietern für Ihre Organisation in Skype für Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Ausführliche Informationen über das Cmdlet " **New-CSAllowedDomain** " verwenden, um eine Domäne hinzuzufügen finden Sie unter [New-CsAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Eine Skype für Business Online-Kunden kann mehrere Domänen verfügen. Wenn Sie einen Verbund mit mehr als einer der Domänen konfigurieren möchten, müssen Sie Konfigurieren der Unterstützung für jede einzelne Domäne mit dem Sie den Verbund zu unterstützen möchten, und der Administrator die Skype für Business Online-Kunden muss für die einzelnen Domänen für Verbund aktivieren federated sein.

  - Konfigurieren der Unterstützung für den Hostinganbieter von der Skype für Business Online Kundendomäne mit dem Sie verbinden möchten. Verwenden Sie das Verfahren in diesem Abschnitt Konfigurieren der Unterstützung für das Hosten von Anbieter.

    > [!NOTE]  
    > Dieser Schritt ist nur für den Partnerverbund mit einer Domäne einen Skype für Business Online-Kunden, nicht für den Verbund mit einer Domäne, die lokal bereitgestellt am Standort eines verbundpartners ist erforderlich.


### <a name="to-configure-support-for-a-hosting-provider"></a>Konfigurieren der Unterstützung für einen Hostinganbieter

1.  Starten Sie aus einem Front-End-Server, der Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.

2.  Führen Sie das **New-CsHostingProvider** -Cmdlet zum Erstellen und Konfigurieren der Hostinganbieter. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **Identität** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter, den Sie erstellen. Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) für die vom Hostinganbieter verwendete Proxyserver. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **VerificationLevel** gibt an, wie (oder ob) von einem Hostinganbieter gesendete Nachrichten überprüft werden, um sicherzustellen, dass sie von diesem Anbieter gesendet wurden.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True ** festgelegt ist.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype für Business Server-Konten verwendet wird. Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.
    
      - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype für Business Server-Topologie enthalten ist.
    
    Ausführliche Informationen zur Verwendung dieser Cmdlets finden Sie unter [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Konfigurieren Sie Benutzerzugriff für den Verbund mit einer Skype für Business Online-Kunden 

Sie müssen den Benutzer konfigurieren Konten von allen Benutzern in Ihrer Organisation in der Reihenfolge für diese Kommunikation mit Verbundpartnern zugelassen werden. Diese Konfiguration gilt für alle Verbundpartner, einschließlich alle Microsoft Skype für Business Online Kunden Domänen mit denen Sie den Verbund zu unterstützen. Ausführliche Informationen zum Konfigurieren von verbundunterstützung für Benutzerkonten finden Sie unter [Konfigurieren von Richtlinien zur Steuerung des Benutzerzugriffs federated](../external-access-policies/configure-policies-to-control-federated-user-access.md) und [weisen Sie eine Zugriffsrichtlinie externer Benutzer auf einen Skype für Business aktivierten Benutzer](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Überprüfen Sie die Kommunikation mit einem Skype für Business Online-Kunden in Skype für Business Server

Um Skype für Unternehmensbenutzer in Ihrer Organisation zur Kommunikation mit Benutzern von einem Skype für Business Online-Kunden zu aktivieren, müssen Sie die folgenden Schritte ausgeführt haben:

  - Alle erforderlichen Komponenten für erfüllt. Dazu gehören Ihrer internen Bereitstellung und Edge-Servern, die Aktivierung des Verbunds für Ihre Organisation und Einrichten von Benutzerkonten unterstützen. Weitere Informationen hierzu finden Sie unter [Voraussetzungen für den Partnerverbund mit einem Skype für Business Online-Kunden](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Access-Unterstützung in Ihrer internen Bereitstellung konfigurierte Domäne. Dies umfasst einen Eintrag Host Anbieter erstellen und Konfigurieren der Bereitstellung von aus der Skype für Business Online Kunden Domäne zugreifen können. Weitere Informationen hierzu finden Sie unter [Configure Verbund für einen Skype für Business Online-Domäne zu unterstützen](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Konfiguriert die Benutzerkonten, um den Verbund zu unterstützen. Weitere Informationen hierzu finden Sie unter [Configure Benutzerzugriff für den Verbund mit einer Skype für Business Online-Kunden](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Schließen Sie alle folgenden Schritte aus, und der Administrator die Skype für Business Online-Kunden alle ihre online-Dienste zur Unterstützung des Verbunds mit Ihrer Organisation-Konfiguration abgeschlossen ist, überprüfen Sie die Kommunikation durch das Testen der Kommunikation zwischen einer Interner Benutzer in Ihrer Organisation und dem Benutzer von der Skype für Business Online-Kunden. Wenn Kommunikation nicht erfolgreich ist, verwenden Sie das Protokollierungstool von den Edge-Server, um die Protokoll- und Ablaufverfolgungsprotokoll-Dateien erfassen, um das Problem zu beheben. 