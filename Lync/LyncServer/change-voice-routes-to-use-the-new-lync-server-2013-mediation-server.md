---
title: Ändern der VoIP-Routen für die Verwendung des neuen Lync Server 2013-Vermittlungsservers
TOCTitle: Ändern der VoIP-Routen für die Verwendung des neuen Lync Server 2013-Vermittlungsservers
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205162(v=OCS.15)
ms:contentKeyID: 49295072
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern der VoIP-Routen für die Verwendung des neuen Lync Server 2013-Vermittlungsservers

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

In diesem Verfahren werden die VoIP-Routen so geändert, dass sie den Lync Server 2013-Vermittlungsserver anstelle des Office Communications Server 2007 R2-Vermittlungsservers der Vorversion verwenden.

## So ändern Sie die VoIP-Routen für die Verwendung des neuen Vermittlungsservers

1.  Systemsteuerung für Lync Server 2013

2.  Wählen Sie im linken Bereich **VoIP-Routing** und dann **Route** aus.

3.  Klicken Sie auf **Neu** , um eine neue VoIP-Route zu erstellen.

4.  Füllen Sie die folgenden Felder aus:
    
      - **Name** : Geben Sie einen beschreibenden Namen für die VoIP-Route ein. Im Rahmen dieses Dokuments wird **W15PSTNRoute** verwendet.
    
      - **Beschreibung** : Geben Sie eine kurze Beschreibung für die VoIP-Route ein.

5.  Überspringen Sie alle verbleibenden Abschnitte, bis Sie zu **Zugeordnete Gateways** gelangen. Klicken Sie auf **Hinzufügen** . Wählen Sie das neue Standardgateway aus, und klicken Sie auf **OK** .

6.  Klicken Sie unter **Zugeordnete PSTN-Verwendungen** auf **Auswählen** .

7.  Wählen Sie auf der Seite **PSTN-Verwendungseintrag auswählen** den Namen eines Eintrags aus, klicken Sie dann auf **OK** .

8.  Klicken Sie auf der Seite **Neue VoIP-Route** auf **OK** , um die **VoIP-Route** zu erstellen.

9.  Klicken Sie auf der Seite **VoIP-Routing** auf **Route** .

10. Verschieben Sie die neu erstellte Route an den Anfang der Liste, und wählen Sie dann **Commit** aus.

