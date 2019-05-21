---
title: Konfigurieren der Unterstützung für Partnerverbund mit einem Skype for Business Online-Kunden
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Wenn Sie Skype for Business in Ihrer Organisation bereitstellen, können Sie sich mit den Domänen eines oder mehrerer Skype for Business Online-Kunden vereinigen. '
ms.openlocfilehash: c6cf36abbbf8876a8aa349d4576b45220517b89e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280110"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Konfigurieren der Föderations Unterstützung für einen Skype for Business Online-Kunden in Skype for Business Server 

Sie können den Benutzern in Ihrer Organisation auf eine der folgenden Arten Kommunikationsdienste bereitstellen:

  - Bereitstellen von Skype for Business Server in Ihrer Organisation (als *Lokale Dienste*bezeichnet) und Einrichten von Skype for Business-Benutzerkonten in Ihrer Organisation
  - Einrichten eines Microsoft Skype for Business Online-Kundenkontos bei einem Hostinganbieter und Einrichten von Benutzerkonten beim Hostinganbieter (so genannte *Online Dienste*).

Wenn Sie Skype for Business in Ihrer Organisation bereitstellen, können Sie sich mit den Domänen eines oder mehrerer Skype for Business Online-Kunden vereinigen. Um die Föderation zwischen Benutzern Ihrer lokalen Skype for Business-Bereitstellung und Benutzern eines Skype for Business Online-Kunden zu aktivieren, müssen Sie die Unterstützung für die Domäne und die Benutzer des Skype for Business Online-Kunden konfigurieren.

> [!NOTE]  
> In dieser Dokumentation werden nur die Verfahren zum Konfigurieren Ihrer Organisation zur Unterstützung der Föderation mit einem Skype for Business Online-Kunden beschrieben. In dieser Dokumentation werden die Verfahren zum Konfigurieren des Skype for Business Online-Kunden zur Unterstützung der Föderation nicht beschrieben. 

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>Voraussetzungen für die Föderation mit einem Skype for Business Online-Kunden

Um mit einem Skype for Business Online-Kunden zu verbünden, sollten Sie die anfängliche Bereitstellung und Konfiguration von Skype for Business Server in Ihrer Organisation bereits abgeschlossen haben. Dazu gehört Folgendes:

  - Bereitstellen von mindestens einem Standard Edition-Server oder einem Enterprise Edition-Front-End-Pool in Ihrer Organisation 
  - Aktivieren interner Benutzerkonten für Skype for Business Server. 
  - Bereitstellen von mindestens einem Edgeserver und den anderen Komponenten, die für die Unterstützung des Zugriffs durch externe Benutzer erforderlich sind Ausführliche Informationen finden Sie unter [Verwalten des Föderations-und externen Zugriffs auf Skype for Business Server](../managing-federation-and-external-access.md).
  - Aktivieren der Föderations Unterstützung in Ihrer Organisation und Konfigurieren der geeigneten Methode zum Steuern des Zugriffs durch Verbunddomänen. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs](../access-edge/enable-or-disable-remote-user-access.md) und [Verwalten von SIP-Verbund Anbietern für Ihre Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md).
  - Aktivieren des Zugriffs externer Benutzer für Benutzer in Ihrer Organisation Ausführliche Informationen finden Sie unter [Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer zu einem Skype for Business-aktivierten Benutzer](../external-access-policies/assign-an-external-user-access-policy.md).



## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>Konfigurieren der Föderations Unterstützung für eine Skype for Business Online-Domäne

Für die Föderation mit einem Skype for Business Online-Kunden müssen Sie die folgenden Schritte ausführen:

  - Konfigurieren Sie die Unterstützung für die Domäne des Skype for Business Online 2010-Kunden (beispielsweise contoso.onmicrosoft.com). Wie in den [Voraussetzungen für die Föderation mit einem Skype for Business Online-Kunden](#prerequisites-for-federating-with-a-skype-for-business-online-customer)angegeben, sollten Sie die Föderation für Ihre Organisation bereits aktiviert haben. Für das Aktivieren der Föderation müssen Sie die Methode angeben, die zum Steuern des Zugriffs durch Verbunddomänen verwendet werden soll. Wenn Sie Ihre Organisation für die Verwendung der Ermittlung konfiguriert haben, ist das Hinzufügen der Domäne zur Liste der zulässigen Organisationen in Ihrer Organisation optional. Wenn Sie die Domänen Erkennung nicht aktiviert haben, müssen Sie den Domänennamen des Skype for Business Online-Kunden der Liste zugelassene Domänen hinzufügen. Sie können einen Domänennamen entweder über die Skype for Business Server-Systemsteuerung oder durch Ausführen des Cmdlets **New-CSAllowedDomain** hinzufügen. Details zur Verwendung der Skype for Business Server-Systemsteuerung, einschließlich der Aktivierung der Domänen Erkennung, finden Sie unter [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md). Details zur Verwendung des Cmdlets **New-CSAllowedDomain** zum Hinzufügen einer Domäne finden Sie unter [New-CSAllowedDomain](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAllowedDomain).

    > [!NOTE]  
    > Ein Skype for Business Online-Kunde kann über mehrere Domänen verfügen. Wenn Sie eine Föderation mit mehr als einer der Domänen durchführen möchten, müssen Sie die Unterstützung für jede einzelne Domäne konfigurieren, für die Sie die Föderation unterstützen möchten, und der Administrator des Skype for Business Online-Kunden muss die Föderation für jede der Domänen aktivieren, um Föderation sein.

  - Konfigurieren Sie die Unterstützung für den Hostinganbieter der Skype for Business Online-Kundendomäne, mit der Sie eine Föderation durchführen möchten. Verwenden Sie das in diesem Abschnitt beschriebene Verfahren, um die Unterstützung für Hostinganbieter zu konfigurieren.

    > [!NOTE]  
    > Dieser Schritt ist nur für den Verbund mit einer Domäne eines Skype for Business Online-Kunden erforderlich, nicht für den Verbund mit einer Domäne, die lokal am Standort eines Partner Partners bereitgestellt wird.


### <a name="to-configure-support-for-a-hosting-provider"></a>So konfigurieren Sie die Unterstützung für einen Hostinganbieter

1.  Starten Sie die Skype for Business Server-Verwaltungsshell von einem Front-End-Server: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsHostingProvider** aus, um den Hostinganbieter zu erstellen und zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **Identity** gibt einen eindeutigen Zeichenfolgenwert Bezeichner für den Hostinganbieter an, den Sie erstellen. Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.
    
      - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.
    
      - **"Verificationlevel"** gibt an, wie (oder ob) Nachrichten, die von einem Hostinganbieter gesendet werden, überprüft werden, um sicherzustellen, dass Sie von diesem Anbieter gesendet wurden.
    
      - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True ** festgelegt ist.
    
      - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.
    
      - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Skype for Business Server-Konten verwendet wird. Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.
    
      - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in Ihrer Skype for Business Server-Topologie enthalten ist.
    
    Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider).

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>Konfigurieren des Benutzerzugriffs für den Verbund mit einem Skype for Business Online-Kunden 

Sie müssen die Benutzerkonten aller Benutzer in Ihrer Organisation so konfigurieren, dass Sie mit Verbundpartnern kommunizieren können. Diese Konfiguration wird für alle Föderationspartner angewendet, einschließlich aller Microsoft Skype for Business Online-Kunden Domänen, mit denen Sie den Verbund unterstützen. Details zum Konfigurieren der Föderations Unterstützung für Benutzerkonten finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern](../external-access-policies/configure-policies-to-control-federated-user-access.md) und [Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer zu einem Skype for Business-aktivierten Benutzer](../external-access-policies/assign-an-external-user-access-policy.md).

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>Überprüfen der Kommunikation mit einem Skype for Business Online-Kunden in Skype for Business Server

Damit Skype for Business-Benutzer in Ihrer Organisation mit Benutzern eines Skype for Business Online-Kunden kommunizieren können, müssen Sie die folgenden Schritte ausgeführt haben:

  - Alle Voraussetzungen erfüllt. Dies umfasst die Bereitstellung von internen und Edge-Servern, das Aktivieren der Föderations Unterstützung für Ihre Organisation und das Einrichten von Benutzerkonten. Ausführliche Informationen finden Sie unter [Voraussetzungen für die Föderation mit einem Skype for Business Online-Kunden](#prerequisites-for-federating-with-a-skype-for-business-online-customer).
  - Konfigurierte Unterstützung für den Domänenzugriff in ihrer internen Bereitstellung. Dies umfasst das Erstellen eines Hostanbieter Eintrags und das Konfigurieren Ihrer Bereitstellung, um den Zugriff aus der Domäne des Skype for Business Online-Kunden zu ermöglichen. Ausführliche Informationen finden Sie unter [Konfigurieren der Föderations Unterstützung für eine Skype for Business Online-Domäne](#configure-federation-support-for-a-skype-for-business-online-domain).
  - Ihre Benutzerkonten wurden für die Unterstützung der Föderation konfiguriert. Ausführliche Informationen finden Sie unter [Konfigurieren des Benutzerzugriffs für den Verbund mit einem Skype for Business Online-Kunden](#configure-user-access-for-federation-with-a-skype-for-business-online-customer).

Nachdem Sie alle diese Schritte ausgeführt haben und der Administrator des Skype for Business Online-Kunden die gesamte Konfiguration seiner Onlinedienste abgeschlossen hat, um den Verbund mit Ihrer Organisation zu unterstützen, überprüfen Sie die Kommunikation, indem Sie die Kommunikation zwischen einer interner Benutzer in Ihrer Organisation und ein Benutzer des Skype for Business Online-Kunden. Wenn die Kommunikation nicht erfolgreich ist, können Sie mithilfe des Protokollierungstools Ihres Edge-Servers Protokoll-und Ablaufverfolgungsdateien aufzeichnen, um das Problem zu beheben. 
