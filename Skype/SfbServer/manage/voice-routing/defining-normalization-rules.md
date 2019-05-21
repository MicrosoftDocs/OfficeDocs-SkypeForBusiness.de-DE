---
title: Definieren von Normalisierungsregeln in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Skype for Business Server-Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um gewählte Telefonnummern in das E. 164-Format zu übersetzen. mit anderen Worten: Normalisierungsregeln nehmen die von einem Benutzer gewählte Telefonnummer an und konvertieren diese Nummer in das Format, das von Skype for Business Server intern verwendet wird. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.'
ms.openlocfilehash: e5156816de13a8d59e3e6eea4890046d5b4f586a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274982"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>Definieren von Normalisierungsregeln in Skype for Business Server

Skype for Business Server-Normalisierungsregeln verwenden reguläre .NET Framework-Ausdrücke, um gewählte Telefonnummern in das E. 164-Format zu übersetzen. mit anderen Worten: Normalisierungsregeln nehmen die von einem Benutzer gewählte Telefonnummer an und konvertieren diese Nummer in das Format, das von Skype for Business Server intern verwendet wird. Jedem Wählplan muss mindestens eine Normalisierungsregel zugewiesen werden.

Details zu Normalisierungsregeln finden Sie unter [Wählpläne und Normalisierungsregeln](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx).

Ausführliche Informationen zum Schreiben regulärer Ausdrücke finden Sie unter [.NET Framework-reguläre Ausdrücke](http://go.microsoft.com/fwlink/p/?linkId=140927).

Mithilfe einer der folgenden Methoden können Sie eine Normalisierungsregel definieren oder bearbeiten:
- [Verwenden Sie das Tool zum **Erstellen einer Normalisierungsregel** ](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) , um Werte für die Anfangsziffern, die Länge, die zu entfernenden Ziffern und die hinzuzufügenden Ziffern anzugeben, und lassen Sie dann die entsprechende übereinstimmende Muster-und Übersetzungsregel von der Skype for Business Server-Systemsteuerung generieren. Für dich.
- [Schreiben Sie reguläre Ausdrücke manuell](#create-or-modify-a-normalization-rule-manually) , um das übereinstimmende Muster und die Übersetzungsregel zu definieren. 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>Erstellen oder Ändern einer Normalisierungsregel mithilfe der Regel zum Erstellen einer Normalisierung

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel in der Skype for Business Server-Systemsteuerung erstellen oder ändern möchten. 

**So definieren Sie eine Regel mithilfe der Regel zum Erstellen einer Normalisierung**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Einzelheiten zu den verschiedenen Methoden, mit denen Sie das Skype Control Panel für Unternehmen starten können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Optional Führen Sie die Schritte unter [Erstellen eines Wählplans](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) bis Schritt 11 aus, oder [Ändern Sie einen Wählplan](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) bis Schritt 10. 
4. Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (beispielsweise **5DigitExtension**).
5. (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).
6. Geben Sie im Abschnitt **Normalisierungsregel erstellen** Werte in die folgenden Felder ein:
    - **Anfangsziffern**: (optional) geben Sie die führenden Ziffern für gewählte Nummern an, die mit dem Muster übereinstimmen sollen. Geben Sie beispielsweise **425** ein, wenn das Muster für gewählte Nummern gelten soll, die mit 425 beginnen.
    - **Length**: Geben Sie die Anzahl der Stellen in dem übereinstimmenden Muster an, und wählen Sie aus, ob das Muster genau mit dieser Länge übereinstimmen soll, wählen Sie Nummern aus, die mindestens diese Länge aufweisen, oder passen Sie gewählte Nummern einer beliebigen Länge an.
    - **Zu entfernende Ziffern**: (optional) geben Sie die Anzahl der Anfangsziffern an, die aus den gewählten Nummern entfernt werden sollen, die das Muster erfüllen soll.
    - Zu **addierende Ziffern**: (optional) geben Sie Ziffern an, die zu gewählten Nummern hinzugefügt werden sollen, damit das Muster übereinstimmt.
    
    Die in diesen Feldern eingegebenen Werte werden in den Feldern **Muster für Vergleich** und **Übersetzungsregel** widergespiegelt. Wenn Sie beispielsweise die **Anfangsziffern** leer lassen, geben Sie **7** in das Feld **Länge** auswählen **genau**ein, und geben Sie **0** in den **zu entfernenden Ziffern**an, der resultierende reguläre Ausdruck in dem **Muster, der übereinstimmen** soll:

    **^ (\d{7}) $**

7. Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein:
    - Ein Wert, der die Anzahl von Ziffern repräsentiert, die im Vergleichsmuster angegeben ist. Wenn das Übereinstimmungsmuster beispielsweise **^ (\d{7}) $** ist, stellt $1 in der Übersetzungsregel siebenstellige Wähl Nummern dar.
    - (Optional) Geben Sie einen Wert in das Feld **Hinzuzufügende Ziffern** ein, um Ziffern anzugeben, die der übersetzten Nummer vorangestellt werden (z. B. **+1425**).
    
    Wenn beispielsweise **Muster für Vergleich** **^{7}(\d) $** als Muster für gewählte Nummern und die **Übersetzungsregel** **+ 1425 $1** als Muster für E. 164-Telefonnummern enthält, normalisiert die Regel 5550100 auf + 14255550100.

8. (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.
9. (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.
    > [!Note] 
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren. Ausführliche Informationen finden Sie unter [Testen des VoIP](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)-Routings. 

10. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.
11. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.
12. Klicken Sie auf der Seite **Wählplan** auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**. 
    > [!Note]
    > Jedes Mal, wenn Sie eine Normalisierungsregel erstellen oder ändern, müssen Sie den Befehl Commit für alle ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter [veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx). 

## <a name="create-or-modify-a-normalization-rule-manually"></a>Manuelles Erstellen oder Ändern einer Normalisierungsregel

Führen Sie die folgenden Schritte aus, wenn Sie eine Normalisierungsregel manuell erstellen oder ändern möchten.

**So definieren Sie eine Normalisierungsregel manuell**

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx).
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die Systemsteuerung zu öffnen. Einzelheiten zu den verschiedenen Methoden, mit denen Sie das Skype Control Panel für Unternehmen starten können, finden Sie unter [Installieren und Öffnen von Verwaltungstools](../../management-tools/install-and-open-administrative-tools.md).
3. Optional Führen Sie die Schritte unter [Erstellen eines Wählplans](GET LINK AFTER MIGRATION) bis Schritt 11 aus, oder [Ändern Sie einen Wählplan](GET LINK AFTER MIGRATION) bis Schritt 10.  
4. Geben Sie unter **Neue Normalisierungsregel** oder **Normalisierungsregel bearbeiten** im Feld **Name** einen beschreibenden Namen für das zu normalisierende Nummernmuster ein (weisen Sie der Normalisierungsregel beispielsweise den Namen **5DigitExtension** zu).
5. (Optional) Geben Sie in **Beschreibung** eine Beschreibung der Normalisierungsregel ein (beispielsweise „Übersetzt 5-stellige Durchwahlnummern“).
6. Klicken Sie in **Normalisierungsregel erstellen** auf **Bearbeiten**.
7. Geben Sie in Regulären Ausdruck eingeben Folgendes ein:
    - Geben Sie in **Dieses Muster abgleichen** das Muster an, das für den Abgleich der gewählten Telefonnummer verwendet werden soll.
    - Geben Sie in **Übersetzungsregel** ein Muster für das Format der übersetzten E.164-Telefonnummern ein.

    Wenn Sie beispielsweise **^{7}(\d) $** in **Übereinstimmung mit diesem Muster** und **+ 1425 $1** in der **Übersetzungsregel**eingeben, normalisiert die Regel 5550100 auf + 14255550100.

8. (Optional) Falls die Normalisierungsregel eine interne Telefonnummer des Unternehmens ergibt, klicken Sie auf **Interne Durchwahl**.
9. (Optional) Geben Sie eine Nummer zum Testen der Normalisierungsregel ein und klicken Sie auf **Los**. Die Testergebnisse werden unterhalb von **Geben Sie eine Testnummer ein** angezeigt.

    > [!Note]
    > Sie können eine Normalisierungsregel speichern, die den Test nicht bestanden hat und sie später neu konfigurieren. Ausführliche Informationen finden Sie unter [Testen des VoIP](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)-Routings. 

10. Klicken Sie auf **OK**, um die Normalisierungsregel zu speichern.
11. Klicken Sie auf **OK**, um die Wähleinstellungen zu speichern.
12. Klicken Sie **** auf der Seite Wählplan **** auf Commi t, und klicken Sie dann auf **alle**übernehmen. 
