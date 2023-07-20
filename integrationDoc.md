# Setup iOS

## Install

````
pod "Ablaevent", "~> 1.0" # Cocoapods 
# OR 
github "AblaAnalytics/ablaevent-ios" # Carthage

````
## Configure Swift

````
import PostHog

let configuration = PHGPostHogConfiguration(apiKey: "phc_ySCF4YinUf6DxprJ5B0jXtzgijeTqFkWPsIIfC3yTrC", host: "https://e.abla.io")

configuration.captureApplicationLifecycleEvents = true; // Record certain application events automatically!
configuration.recordScreenViews = true; // Record screen views automatically!

PHGPostHog.setup(with: configuration)
let posthog = PHGPostHog.shared()

````
## Or configure Objective-C

````
#import <PostHog/PHGPostHog.h>
#import <PostHog/PHGPostHogConfiguration.h>

PHGPostHogConfiguration *configuration = [PHGPostHogConfiguration configurationWithApiKey:@"phc_ySCF4YinUf6DxprJ5B0jXtzgijeTqFkWPsIIfC3yTrC" host:@"https://e.abla.io"];

configuration.captureApplicationLifecycleEvents = YES; // Record certain application events automatically!
configuration.recordScreenViews = YES; // Record screen views automatically!

[PHGPostHog setupWithConfiguration:configuration];

````
## Send an event with swift

````
posthog.capture("Test Event")

````

## Send an event with Objective-C

````
[[PHGPostHog sharedPostHog] capture:@"Test Event"];

````
