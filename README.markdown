# TTTHoursOfOperation
## A sensible library for managing and displaying business hours

Modeling and displaying hours of operation is tricky business. It's perhaps one of the most prolific ratholes that has ever existed--a trap that has ensnared many a venturing programmer with its tendrils of perceived simplicity and maddening edge-cases.

TTTHoursOfOperation makes it easy to programmatically do the following:

    Mon-Wed: 8:00AM - 7:00PM  
    Thu: 9:00AM - 12:00PM, 3:00PM - 10:00PM  
    Fri: Closed  
    Weekends: 11:00AM - 1:00AM

Save yourself a dozen or so maddening hours (go hiking! learn Esperanto!) and try out this library. You'll get the following features for free:

- Clean, minimalist API that you can embed in your project by simply dropping in a single set of `.h` and `.m` files
- Built-in hours parser to handle simply-formatted input, such as `"08:45-15:00,17:00-22:00"` or `"closed"`
- Check if the current time is within today's store hours, or get the NSDates associated with this weeks hours for a particular weekday
- Wrap-around time support, i.e. `"20:00-26:00"` would be the hours 8PM - 2AM, associated with a specified weekday
- Localized output, such that a Japanese user, for example would see hours in a format like "火: 8:00 - 20:00" or "閉店"

## Example Usage

Example project is forthcoming. In the meantime, here's how you can add `TTTHoursOfOperation` into your project:
  
    hoursOfOperation = [[TTTWeeklyHoursOfOperation alloc] init];
    [self.hoursOfOperation setHoursWithString:@"08:00-19:00" forWeekday:TTTMonday];
    [self.hoursOfOperation setHoursWithString:@"08:00-19:00" forWeekday:TTTTuesday];
    [self.hoursOfOperation setHoursWithString:@"08:00-19:00" forWeekday:TTTWednesday];
    [self.hoursOfOperation setHoursWithString:@"09:00-12:00,15:00-22:00" forWeekday:TTTThursday];
    [self.hoursOfOperation setHoursWithString:@"closed" forWeekday:TTTFriday];
    [self.hoursOfOperation setHoursWithString:@"11:00-25:00" forWeekday:TTTSaturday];
    [self.hoursOfOperation setHoursWithString:@"11:00-25:00" forWeekday:TTTSunday];

## License

TTTHoursOfOperation is licensed under the MIT License:

  Copyright (c) 2011 Mattt Thompson (http://mattt.me/)

  Permission is hereby granted, free of charge, to any person obtaining a copy
  of this software and associated documentation files (the "Software"), to deal
  in the Software without restriction, including without limitation the rights
  to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
  copies of the Software, and to permit persons to whom the Software is
  furnished to do so, subject to the following conditions:

  The above copyright notice and this permission notice shall be included in
  all copies or substantial portions of the Software.

  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
  IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
  FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
  AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
  LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
  OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
  THE SOFTWARE.
