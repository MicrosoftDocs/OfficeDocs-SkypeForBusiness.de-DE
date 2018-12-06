---
title: 'Lync Server 2013: Konfiguration des Partnerverbunds für einen Audiokonferenzanbieter'
TOCTitle: Konfiguration des Partnerverbunds für einen Audiokonferenzanbieter
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn510996(v=OCS.15)
ms:contentKeyID: 59954035
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfiguration des Partnerverbunds für einen Audiokonferenzanbieter in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-07-24_

Wenn Sie einen Audiokonferenzanbieter (Audio Conference Provider, ACP) in Ihrer Hybridbereitstellung (lokale Lync Server-Bereitstellung mit Lync Online) verwenden möchten, müssen Sie einen Partnerverbund zwischen Ihrer lokalen Lync-Bereitstellung und dem ACP-Partner als zulässigen Partnerserver konfigurieren. Sie können den Partnerverbund konfigurieren, indem Sie die ACP-Partnerdomäne und den Edgeserver (der möglicherweise auch als Zugriffsproxy bezeichnet wird) zur Partnerverbunddomänenliste für Ihre lokale Bereitstellung hinzufügen. Weitere Details erhalten Sie von Ihrem ACP-Provider. Ihr ACP-Partner muss dann den FQDN Ihres lokalen Edgeserverpools zu seiner zugelassenen Partnerverbunddomänenliste hinzufügen.

  - **Hinzufügen der ACP-Domäne und des Edgeservers als zugelassene Verbunddomäne**
    
    Zum Hinzufügen der ACP-Domäne als zulässiger Partnerserver (zugelassene Partnerverbunddomäne) führen Sie die Schritte unter [Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) aus. Fügen Sie für den Edgeserver den FQDN des Edgeservers des ACP-Partners hinzu. Sie müssen sich möglicherweise an Ihren ACP-Partner wenden, um den FQDN für seinen Edgeserver zu erhalten, der von Ihrem ACP möglicherweise auch als Zugriffsproxy bezeichnet wird.

  - **Bereitstellen des FQDN Ihres Edgeserverpools für den ACP-Partner**
    
    Der ACP-Partner muss einen Partnerverbund konfigurieren, um Ihre lokale Domäne als einen zulässigen Partnerserver hinzuzufügen, indem der FQDN Ihres Edgeserverpools als eine zugelassene Partnerverbunddomäne hinzugefügt wird.

