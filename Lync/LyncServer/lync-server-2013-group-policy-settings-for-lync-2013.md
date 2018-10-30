---
title: Gruppenrichtlinieneinstellungen für Lync 2013
TOCTitle: Gruppenrichtlinieneinstellungen für Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204924(v=OCS.15)
ms:contentKeyID: 49294086
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gruppenrichtlinieneinstellungen für Lync 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In früheren Versionen von Lync und Office Communicator wurde die eigenständige administrative Vorlagendatei "Communicator.adm" zum Konfigurieren der Einstellungen für die Gruppenrichtlinie des Clients zur Verfügung gestellt. In Lync 2013 werden neue administrative Vorlagendateien (ADMX- und ADML-Dateien) zur Verfügung stellt. Außerdem wird die administrative Vorlage für die Office-Gruppenrichtlinie bereitgestellt. Mithilfe der ADMX- und ADML-Dateien von Lync 2013 können Sie Vorlagen herunterladen und die Einstellungen für die Gruppenrichtlinie aller Office-Programme und Sprachpakete zentral verwalten. Nähere Informationen hierzu finden Sie unter "Administrative Vorlagendateien (ADMX, ADML) für Office 2013" in der Office 2013-Dokumentation unter [http://go.microsoft.com/fwlink/?linkid=267516\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=267516%26clcid=0x407).

## Richtlinien für das Clientbootstrapping

Es gibt verschiedene Richtlinien für das Clientbootstrapping, die Sie konfigurieren sollten, bevor sich Benutzer zum ersten Mal beim Server anmelden. Da diese Richtlinien in Kraft treten, bevor sich der Client anmeldet und In-Band-Bereitstellungseinstellungen vom Server empfängt, können Sie diese Richtlinien mithilfe von Gruppenrichtlinien konfigurieren. Weitere Informationen finden Sie in der Bereitstellungsdokumentation unter [Konfigurieren von Richtlinien für das Clientbootstrapping in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md).

