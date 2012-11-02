---
type: rule
title: Do you inject your dependencies?
uri: do-you-inject-your-dependencies
created: 2012-10-19T17:23:08.0000000Z
authors:
- id: 24
  title: Adam Stephensen

---

 
Injecting your dependency gives you:

- Loosely coupled classes
- Increased code reusing
- Maintainable code
- Testable methods
- All dependencies are specified in one place
- Class dependencies are clearly visible in the constructor

 ![inject](/PublishingImages/inject-bad-1.jpg) Figure: Bad Example – A solution where each layer depends on static classes is not maintainable or testable ![inject](/PublishingImages/inject-good-1.jpg) Figure: Good Example – Dependencies in each layer should only be interfaces. This allows dependencies to be easily interchanged and unit tests to be written against mock/fake objects ![inject](/PublishingImages/inject-bad-2.jpg) Figure: Bad Example – Classes should not include dependencies on database classes or business objects. Both of these classes may contain dependencies on external services like web services or databases ![inject](/PublishingImages/inject-good-2.jpg) Figure: Good Example – The dependencies are injected into the class. This enables alternative classes to be injected. For example, a DHLShippingCalculator should be easily substituted for a FedexShippingCalculator. A MockShippingCalculator and MockProductRepository could be injected if we wanted to run unit tests
