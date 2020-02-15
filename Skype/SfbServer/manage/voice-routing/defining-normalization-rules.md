---
title: Definieren von Normalisierungsregeln in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um gewählte Telefonnummern in das E. 164-Format zu übersetzen; mit anderen Worten: Normalisierungsregeln nehmen die von einem Benutzer gewählte Telefonnummer an und wandeln diese Nummer in das Format um, das von Skype for Business Server intern verwendet wird. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.'
ms.openlocfilehash: 42ec43a08d1c155f61869bdfebf07e94ac040e56
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028846"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definieren von Normalisierungsregeln in Skype for Business Server

Skype for Business Server Normalisierungsregeln verwenden .NET Framework reguläre Ausdrücke, um gewählte Telefonnummern in das E. 164-Format zu übersetzen; mit anderen Worten: Normalisierungsregeln nehmen die von einem Benutzer gewählte Telefonnummer an und wandeln diese Nummer in das Format um, das von Skype for Business Server intern verwendet wird. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Ausführliche Informationen zu Normalisierungsregeln finden Sie unter [Dial Plans and normalize Rules](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx).

Ausführliche Informationen zum Schreiben von regulären Ausdrücken finden Sie unter [.NET Framework reguläre Ausdrücke](http://go.microsoft.com/fwlink/p/?linkId=140927).

Mithilfe einer der beiden folgenden Methoden können Sie eine Übersetzungsregel definieren oder bearbeiten:
- [Verwenden Sie das Tool zum **Erstellen einer Normalisierungsregel** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann Skype for Business Server Systemsteuerung das entsprechende Übereinstimmungsmuster und die Übersetzungsregel generieren.
- [Schreiben Sie reguläre Ausdrücke manuell](#create-or-modify-a-normalization-rule-manually) , um das übereinstimmende Muster und die Übersetzungsregel zu definieren. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Erstellen oder Ändern einer Normalisierungsregel mit Normalisierungsregel erstellen

Führen Sie die folgenden Schritte aus, wenn Sie in Skype for Business Server Systemsteuerung eine Normalisierungsregel erstellen oder ändern möchten. 

**So definieren Sie eine Regel mit dem Erstellen einer Normalisierungsregel**

1. Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business-Systemsteuerung verwenden können, finden Sie unter [Install and Open Administration Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Optional Befolgen Sie die Schritte unter [Erstellen eines Wählplans](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) bis Schritt 11 oder [Ändern eines Wählplans](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) bis Schritt 10. 
4. Geben Sie unter **neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen ein, der das im **Namen** normalisierte Nummernmuster beschreibt (beispielsweise **5DigitExtension**).
5. Optional Geben Sie in **Beschreibung**eine Beschreibung der Normalisierungsregel ein (beispielsweise "übersetzt 5-stellige Durchwahlnummern").
6. Geben Sie unter **Normalisierungsregel erstellen**Werte in die folgenden Felder ein:
    - **Starting digits**: (optional) geben Sie die führenden Ziffern von gewählten Nummern an, die mit dem Muster übereinstimmen sollen. Geben Sie beispielsweise **425** ein, wenn das Muster mit den gewählten Nummern beginnend mit 425 übereinstimmen soll.
    - **Length**: Geben Sie die Anzahl der Ziffern im übereinstimmenden Muster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, wählen Sie Nummern aus, die mindestens diese Länge aufweisen, oder passen Sie gewählte Nummern einer beliebigen Länge an.
    - **Zu entfernende Ziffern**: (optional) geben Sie die Anzahl der Anfangsziffern an, die aus gewählten Nummern entfernt werden sollen, die mit dem Muster übereinstimmen sollen.
    - **Hinzuzufügende Ziffern**: (optional) geben Sie Ziffern an, die zu gewählten Nummern hinzugefügt werden sollen, die mit dem Muster übereinstimmen sollen.
    
    Die Werte, die Sie in diese Felder eingeben, werden in **Übereinstimmung mit Muster** und **Übersetzungsregel**übernommen. Wenn Sie beispielsweise **Start Ziffern** leer lassen, geben Sie **7** in das Feld **length** Select **Exact**ein, und geben Sie **0** in **zu entfernende Ziffern**an, sodass der resultierende reguläre Ausdruck im Muster mit folgendem **übereinstimmt** :

    **^ (\d{7}) $**

7. Geben Sie in **Übersetzungsregel**ein Muster für das Format der übersetzten E. 164-Telefonnummern wie folgt an:
    - Ein Wert, der die Anzahl der im übereinstimmenden Muster angegebenen Ziffern darstellt. Wenn das übereinstimmende Musterbeispiels Weise **^ (\d{7}) $** ist, stellt $1 in der Übersetzungsregel siebenstellige gewählte Nummern dar.
    - Optional Geben Sie einen Wert in das Feld **Ziffern hinzufügen** ein, um Ziffern anzugeben, die der übersetzten Zahl vorangestellt werden sollen (beispielsweise **+ 1425**).
    
    Wenn beispielsweise das Muster "Match" mit **^ ({7}\d) $** **übereinstimmt** , da das Muster für gewählte Nummern und die **Übersetzungsregel** **+ 1425 $1** als Muster für E. 164-Telefonnummern enthält, normalisiert die Regel 5550100 bis + 14255550100.

8. Optional Wenn die Normalisierungsregel eine interne Telefonnummer für Ihre Organisation ergibt, wählen Sie **interne Durchwahl**aus.
9. Optional Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **go**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    > [!Note] 
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht besteht, und Sie dann später neu konfigurieren. Ausführliche Informationen finden Sie unter [Testen der VoIP](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)-Weiterleitung. 

10. Klicken Sie auf **OK** , um die Normalisierungsregel zu speichern.
11. Klicken Sie auf **OK** , um die Wähleinstellungen zu speichern.
12. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commit** und anschließend auf **Commit für alle**. 
    > [!Note]
    > Wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl Commit all ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Manuelles Erstellen oder Ändern einer Normalisierungsregel

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten.

**So definieren Sie eine Normalisierungsregel manuell**

1. Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die admin-URL ein, um die Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten der Skype for Business-Systemsteuerung verwenden können, finden Sie unter [Install and Open Administration Tools](../../management-tools/install-and-open-administrative-tools.md).
3. Optional Befolgen Sie die Schritte unter [Erstellen eines Wählplans](GET LINK AFTER MIGRATION) bis Schritt 11 oder [Ändern eines Wählplans](GET LINK AFTER MIGRATION) bis Schritt 10.  
4. Geben Sie unter **neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten**einen Namen ein, der das im **Namen** normalisierte Nummernmuster beschreibt (beispielsweise den Namen Normalisierungsregel **5DigitExtension**).
5. Optional Geben Sie in **Beschreibung**eine Beschreibung der Normalisierungsregel ein (beispielsweise "übersetzt 5-stellige Durchwahlnummern").
6. Klicken Sie in **Normalisierungsregel erstellen**auf **Bearbeiten**.
7. Geben Sie in Regulären Ausdruck eingeben Folgendes ein:
    - Geben Sie unter **dieses Muster abgleichen**das Muster an, das Sie für die Übereinstimmung mit der gewählten Telefonnummer verwenden möchten.
    - Geben Sie in **Übersetzungsregel**ein Muster für das Format der übersetzten E. 164-Telefonnummern an.

    Wenn Sie beispielsweise **^{7}(\d) $** in **mit diesem Muster** und **+ 1425 $1** in der **Übersetzungsregel**eingeben, normalisiert die Regel 5550100 bis + 14255550100.

8. Optional Wenn die Normalisierungsregel eine interne Telefonnummer für Ihre Organisation ergibt, wählen Sie **interne Durchwahl**aus.
9. Optional Geben Sie eine Zahl ein, um die Normalisierungsregel zu testen, und klicken Sie dann auf **go**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!Note]
    > Sie können eine Normalisierungsregel speichern, die den Test noch nicht besteht, und Sie dann später neu konfigurieren. Ausführliche Informationen finden Sie unter [Testen der VoIP](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)-Weiterleitung. 

10. Klicken Sie auf **OK** , um die Normalisierungsregel zu speichern.
11. Klicken Sie auf **OK** , um die Wähleinstellungen zu speichern.
12. Klicken Sie auf der Seite **Wähleinstellungen** auf **Commi**t, und klicken Sie dann auf **Commit für alle**. 
