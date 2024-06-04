# Migrator

An extension for everyone to migrate their extension code from AI2 to another builder.

App Inventor Sources, Niotron IDE & Extension Templates - RUSH

## Tutorial

Step 1. Type your code in the Codebox.

Step 2. Click The Migrate Code Button.

Step 3. Paste it using (CTRL + V) to your Computer

Step 4. Open your favorite ide for RUSH

Step 5. Your code may look like this: package com.bextdev.accountid;

Extension made by Bextdev
written 6/3/2024

import android.app.Activity;
import android.content.Context;
import com.google.appinventor.components.annotations.*;
import com.google.appinventor.components.common.ComponentCategory;
import com.google.appinventor.components.runtime.AndroidNonvisibleComponent;
import com.google.appinventor.components.runtime.ComponentContainer;
import com.google.appinventor.components.runtime.EventDispatcher;

String
String

String

String

public class AccountId extends AndroidNonvisibleComponent {

    Activity and Context
    private Context context;
    private Activity activity;
    private String accountId; 

    public AccountId(ComponentContainer container) {
        super(container.$form());
        this.activity = container.$context();
        this.context = container.$context();
    }

    @SimpleFunction(description = "Get Account Id by typing Discourse Community Profile Link")
    public void GetDiscourseAccountId(String profileLink) {
        String cleanedProfileLink = profileLink.replaceFirst("https?://", "");

        if(cleanedProfileLink.contains("/u/")){
            String[] parts = cleanedProfileLink.split("/u/");
            if(parts.length > 1){
                accountId = parts[1].split("/")[0];
            } 
        } else if(cleanedProfileLink.contains("/summary/")){
            String[] parts = cleanedProfileLink.split("/summary/");
            if(parts.length > 0){
                accountId = parts[0].split("/")[parts[0].split("/").length - 1];
            }
       } else if(cleanedProfileLink.contains("/activity/")){
            String[] parts = cleanedProfileLink.split("/activity/");
            if(parts.length > 0){
                accountId = parts[0].split("/")[parts[0].split("/").length - 1];
            }
       } else if(cleanedProfileLink.contains("/badges/")){
            String[] parts = cleanedProfileLink.split("/badges/");
            if(parts.length > 0){
                accountId = parts[0].split("/")[parts[0].split("/").length - 1];
            }
       }  else if(cleanedProfileLink.contains("/notification/")){
            String[] parts = cleanedProfileLink.split("/notification/");
            if(parts.length > 0){
                accountId = parts[0].split("/")[parts[0].split("/").length - 1];
            }
       } else if(cleanedProfileLink.contains("/messages/")){
            String[] parts = cleanedProfileLink.split("/messages/");
            if(parts.length > 0){
                accountId = parts[0].split("/")[parts[0].split("/").length - 1];
            }
       } else if(cleanedProfileLink.contains("/follow/feed/")){
            String[] parts = cleanedProfileLink.split("/follow/feed");
            if(parts.length > 0){
                accountId = parts[0].split("/")[parts[0].split("/").length - 1];
            }
       } else if(cleanedProfileLink.contains("/preferences/account/")){
            String[] parts = cleanedProfileLink.split("/preferences/account");
            if(parts.length > 0){
                accountId = parts[0].split("/")[parts[0].split("/").length - 1];
            }
       }

       if(accountId != null){
           AccountId(accountId);
       }
    }

    @SimpleEvent(description = "Returns the AccountId")
    public void AccountId(String accountId) {
        EventDispatcher.dispatchEvent(this, "AccountId", accountId);
    }
} so if you want to remove the 4 strings or maybe more simply select them and use the DELETE Shortcut (CTRL + D) or use the delete key in your keyboard.

**NOTE 1:** the @Options annotation (parameter) maybe removed but it will be replaced by a String Parameter so if you want to remove the String Parameter just simply do the Delete Shortcut (CTRL + D) in your keyboard. 
But if you have for example @SimpleFunction
                            public @Options(YourFileName.class)ExampleMethod(@Options(YourFileName.class)String animal){

                            }
If the @Options (beside the public) is deleted if you want to ignore the String just ignore but if you want to replace you replace it. 

**NOTE 2:** the @Options annotations (parameter) will be replaced by String parameter so if you want to ignore it. Just Ignore It Don't Follow NOTE 1
