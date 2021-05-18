# Foobar

Foobar is a Python library for dealing with word pluralization.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install foobar.

```bash
pip install foobar
```

## Usage

```java
package in.mintset.data.proxy;

import in.mintset.model.kite.OfflineData;
import org.springframework.cloud.openfeign.FeignClient;
import org.springframework.http.MediaType;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestHeader;
import org.springframework.web.bind.annotation.RequestParam;

@FeignClient(name = "kite-offline", url = "https://kite.zerodha.com/oms/instruments/historical")
public interface ZerodhaOfflineProxy {

  @GetMapping(
      value = "/{instrumentId}/{period}?user_id=YP1618&oi=1",
      consumes = MediaType.APPLICATION_JSON_VALUE)
  OfflineData getData(
      @RequestHeader("authorization") String authorization,
      @PathVariable("instrumentId") Long instrumentId,
      @PathVariable("period") String period,
      @RequestParam(name = "from") String from,
      @RequestParam(name = "to") String to);
}

```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
