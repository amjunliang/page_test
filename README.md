 

[ReactiveCocoa](https://github.com/ReactiveCocoa/ReactiveCocoa) 17.5k Facebook



[KVOController](https://github.com/facebook/KVOController) 58k Facebook

```objective-c
[self.KVOController observe:self.fizz
                    keyPath:@"number"
                    options:NSKeyValueObservingOptionNew | NSKeyValueObservingOptionOld
                      block:^(id  _Nullable observer, id  _Nonnull object, NSDictionary<NSString    *,id> * _Nonnull change) {
                          NSLog(@"%@", change);
                      }];
```

[THObserversAndBinders](https://github.com/th-in-gs/THObserversAndBinders) 639 个人

```objective-c
//kvo
[THObserver observerForObject:object
                      keyPath:@"propertyToObserve"
                      options:NSKeyValueObservingOptionInitial | NSKeyValueObservingOptionNew
                  changeBlock:^(NSDictionary *change) {
                      NSLog(@"propertyToObserve is %@", change[NSKeyValueChangeNewKey]);
                  }];
//绑定
[THBinder binderFromObject:fromObject keyPath:@"fromKey"
                  toObject:toObject keyPath:@"toKey"];

[THBinder binderFromObject:fromObject keyPath:@"fromKey"
                                     toObject:toObject keyPath:@"toKey"
                          transformationBlock:^id(id value) {
                              return @([value integerValue] + 5);
                          }];
```

[RZDataBinding](https://github.com/Raizlabs/RZDataBinding) 345 个人

```objective-c
    ///绑定模型的属性到ui
[cell.textLabel rz_bindKey:RZDB_KP(UILabel, text) toKeyPath:RZDB_KP(RZUser, fullName) ofObject:user];
    //绑定模型的属性到UI, 并且转化数据
    [cell.imageView rz_bindKey:RZDB_KP(UIImageView, image) toKeyPath:RZDB_KP(RZUser, favoriteColorHex) ofObject:user withTransform:^id(id value) {
        UIColor *color = [UIColor rz_hexColor:(uint32_t)[value integerValue]];
        return [UIImage rz_imageWithColor:color size:CGSizeMake(35.0f, 35.0f)];
    }];
```


