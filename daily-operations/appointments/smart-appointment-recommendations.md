---
description: >-
  Let SimpleSpa suggest a client's next appointment based on their past booking
  history.
---

# Smart Appointment Recommendations

SimpleSpa can automatically suggest a client’s next appointment based on their past booking history.

This feature looks at a client’s service patterns, timing preferences and preferred staff, and proposes an ideal date and time for their next visit.

## How it works

When you open an existing appointment on your calendar, SimpleSpa reviews the client’s recent booking history to:

* Identify their most frequently booked service(s).
* Detect their typical booking cadence (for example, every 2 weeks or every month).
* Recognize their preferred time of day and staff member.

It then recommends the next best appointment to keep the client on their usual schedule.

## Using Smart Appointment Recommendations

{% stepper %}
{% step %}
### Open the appointment

In the **Calendar** view, click the client’s appointment to open the appointment details dialog.
{% endstep %}

{% step %}
### Click the lightning button ⚡

Look for the lightning icon in the appointment dialog toolbar. This is the **Smart Recommendation** button.
{% endstep %}

{% step %}
### View the suggested booking

After a quick analysis, a pop-up shows the recommended:

* **Service** (for example, “Awesome Cut”)
* **Date** (for example, “2025-09-12”)
* **Time** (for example, “14:00”)
* **Staff** (if a clear preference is found)
{% endstep %}

{% step %}
### Apply the recommendation

Use the suggested details to quickly create a new booking for the client.
{% endstep %}
{% endstepper %}

## Notes

* If there is not enough booking history, the feature may not be able to make a strong recommendation.
* The system uses both AI-powered and non-AI fallback logic so you always get the best suggestion possible.
* Recommendations are based on historical patterns and do not book the appointment automatically. You choose whether to apply them.

## Related

* [Creating an Appointment](creating-an-appointment.md)
* [New Appointment Wizard](new-appointment-wizard.md)
