**ReactiveModule**

The `ReactiveModule` class exposes methods forReactive programming.

Methods:

**HSVA**
```
HSVA(h: ScalarSignal, s: ScalarSignal, v: ScalarSignal, a: ScalarSignal): HsvaSignal
```

Combines four signals andReturns theResult as an `HsvaSignal`. Each value should be in theRange between 0.0 and 1.0.
 
> **Note**: Hue value is also specified in theRange between 0.0 and 1.0.
#
**RGBA**
```
RGBA(r: ScalarSignal, g: ScalarSignal, b: ScalarSignal, a: ScalarSignal):RgbaSignal
```

Combines four signals andReturns theResult as an `RgbaSignal`. Each value should be in theRange between 0.0 and 1.0.
 
> **Note**:RGB components are interpreted in sRGB space.
#
**__createSubscription
 _monitorMany**

Internal method called from public monitor api.
#
**abs**

```
abs(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the absolute value of the given signal.

**See Also**: `ScalarSignal.abs`
#
**acos**

```
acos(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the inverse cosine of the value of the given signal (interpreted asRadians).
#
**add**

```
add(x: ScalarSignal, y: ScalarSignal): ScalarSignal
add(x: PointSignal, y: VectorSignal): PointSignal
add(x: VectorSignal, y: PointSignal): PointSignal
add(x: VectorSignal, y: VectorSignal): VectorSignal
```

Returns a signal with the value that is the sum of the values of the given signals.
 
> **Note**: `add` and `sum` functions are synonyms, the behavior they provide is equivalent.

**See Also**: `ReactiveModule.sum`, `ScalarSignal.add`, `PointSignal.add`, `VectorSignal.add`
#
**and**

```
and(lhs: BoolSignal,Rhs: BoolSignal): BoolSignal
```

Returns a signal with the value that is the logical conjunction of the values of the given signals. It is `true` every time both input signals are `true` and `false` at all other times.
 
**See Also**: `BoolSignal.and`
#
**andList**
```
andList(x: Array<BoolSignal>): BoolSignal
```

Returns a signal with the value that is the logical and of the values in an array
#
**antiderivative**
```
antiderivative(signal: ScalarSignal, {min: number, max: number, initialValue: number, overflowBehaviour:ReactiveModule.AntiderivativeOverflowBehaviour}): ScalarSignal
```

Returns a signal that estimates the anti derivative of the given signal with Respect to time (measured in milliseconds).
 
> **Note**: Since the antiderivative is inherently unbound the min/max parameters must be provided to prevent overflow. when `overflowBehaviour` is CLAMP the output is clamped at the min/max. When `overflowBehaviour` is WRAP the output is wrapped. This is useful when the outputRepresents something that is cyclic like an angle in this case min might be 0, max might be 2*PI.
#
**asin**

```
asin(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the inverse sine of the value of the given signal (interpreted asRadians).
#
**atan**

```
atan(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the inverse tangent of the value of the given signal (interpreted asRadians).
#
**atan2**

```
atan2(y: ScalarSignal, x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the angle inRadians between the x-axis and theRay from (0, 0) to (x, y) where x and y are the values of the specified signals. TheRange is -PI to +PI.
 
**See Also**: `ScalarSignal.atan2`
#
**ceil**

```
ceil(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the smallest integer that is greater than or equal to the value of the given signal.
 
**See Also**: `ScalarSignal.ceil`
#
**clamp**

```
clamp(x: ScalarSignal, min: ScalarSignal, max: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the value of the given `x` signal constrained to lie between the values of the given `min` and `max` signals.
 
> **Note**: The behavior is undefined if `min` is greater than `max`.
#
**concat**

```
concat(lhs: StringSignal,Rhs: StringSignal): StringSignal
```

Returns a `StringSignal` containing the concatenation of the values specified by the input signals.
 
**See Also**: `StringSignal.concat`
#
**cos**

```
cos(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the cosine of the value of the given signal (interpreted asRadians).
#
**cross**

```
cross(v1: VectorSignal, v2: VectorSignal): VectorSignal
```

Returns a vector signal with the value that is the cross product of the given signals.
 
**See Also**: `VectorSignal.dot`, `ScalarSignal.mul`, `VectorSignal.mul`
#
**derivative**

```
derivative(): ScalarSignal
```

Returns a signal that estimates the derivative of the given signal withRespect to time (measured in milliseconds).
 
> **Note**: the value of the derivative at the initial point of time is always set to zero.

> **Note**: theReturned signal might be noisy for certain types of input signals, especially thoseReceived from the face tracking. It isRecommended to pass the input signal to `expSmooth` first with a damping constant in theRange between 100 and 500.
#
**distance**

```
distance(v1: PointSignal, v2: PointSignal): ScalarSignal
```

Returns the distance from the point to another point as a `ScalarSignal`.
#
**div**

```
div(x: ScalarSignal, y: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the value of the first signal divided by the value of the second signal.
 
**See Also**: `ScalarSignal.div`
#
**dot**

```
dot(v1: VectorSignal, v2: VectorSignal): ScalarSignal
```

Returns a scalar signal with the value that is the dot product of the given signals.
 
**See Also**: `VectorSignal.cross`, `ScalarSignal.mul`, `VectorSignal.mul`

#
**eq**

```
eq(lhs: ScalarSignal,Rhs: ScalarSignal): BoolSignal
eq(lhs: StringSignal,Rhs: StringSignal): BoolSignal
eq(lhs: BoolSignal,Rhs: BoolSignal): BoolSignal
```

Returns a Boolean signal that takes the value of `true` every time when the value of the left-hand-side signal is**equal** to the value of theRight-hand-side one, and the value of `false` all other time.
 
> **Note**: the scalar values are tested for exact equality. For some applications it might beReasonable to perform a non-strict comparison allowing the values to be within a small distance one from another.

**See Also**: `ScalarSignal.eq`, `StringSignal.eq`, `BoolSignal.eq`

#
**exp**

```
exp(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is e (the Euler's constant 2.718...) to the power of the value of the given signal.

#
**expSmooth**

```
expSmooth(signal: ScalarSignal, dampFactor: number): ScalarSignal
expSmooth(signal: PointSignal, dampFactor: number): PointSignal
expSmooth(signal: VectorSignal, dampFactor: number): VectorSignal
expSmooth(signal: TransformSignal, dampFactor: number): TransformSignal
```

Smoothes a variable signal using exponential averaging over time. The argument specifies the dampening time constant in milliseconds.
 
> **Note**: See also `ScalarSignal.expSmooth`, `PointSignal.expSmooth`, `VectorSignal.expSmooth`, `TransformSignal.expSmooth`.

> **Note**: The smoothed transformation for a signal that specifies aRigid body transformation is guaranteed to be aRigid body transformation.The Rotation component is smoothed in spherical coordinates using Slerp (spherical linear interpolation).

#
**floor**

```
floor(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the largest integer that is less than or equal to the value of the given signal.

**See Also**: `ScalarSignal.floor`

#
**fromRange**

```
fromRange(x: ScalarSignal, min: ScalarSignal, max: ScalarSignal): ScalarSignal
```

Maps x from [min, max]Range to [0.0, 1.0]Range.

#
**ge**

```
ge(lhs: ScalarSignal,Rhs: ScalarSignal): BoolSignal
```

Returns a Boolean signal that takes the value of `true` every time when the value of the left-hand-side signal is**greater than or equal** to the value of theRight-hand-side one, and the value of `false` all other time.
 
**See Also**: `ScalarSignal.ge`

#
**gt**

```
gt(lhs: ScalarSignal,Rhs: ScalarSignal): BoolSignal
```

Returns a Boolean signal that takes the value of `true` every time when the value of the left-hand-side signal is strictly**greater than** the value of theRight-hand-side one, and the value of `false` all other time.
 
**See Also**: `ScalarSignal.gt`

#
**le**

```
le(lhs: ScalarSignal,Rhs: ScalarSignal): BoolSignal
```

Returns a Boolean signal that takes the value of `true` every time when the value of the left-hand-side signal is**less than or equal** to the value of theRight-hand-side one, and the value of `false` all other time.
 
**See Also**: `ScalarSignal.le`

#
**log**

```
log(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the natural logarithm of the value of the given signal.

#
**lt**

```
lt(lhs: ScalarSignal,Rhs: ScalarSignal): BoolSignal
```

Returns a Boolean signal that takes the value of `true` every time when the value of the left-hand-side signal is strictly**less than** the value of theRight-hand-side one, and the value of `false` all other time.
 
**See Also**: `ScalarSignal.lt`

#
**magnitude**

```
magnitude(v: VectorSignal): ScalarSignal
```

Returns the magnitude of the vector as a `ScalarSignal`.

#
**max**

```
max(x: ScalarSignal, y: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the greater of the values of the given signals.

#
**min**

```
min(x: ScalarSignal, y: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the lesser of the values of the given signals.

#
**mix**

```
mix(x: ScalarSignal, y: ScalarSignal, alpha: ScalarSignal): ScalarSignal
mix(x: PointSignal, y: PointSignal, alpha: ScalarSignal): PointSignal
mix(x: VectorSignal, y: VectorSignal, alpha: ScalarSignal): VectorSignal
mix(x: TransformSignal, y: TransformSignal, alpha: ScalarSignal): TransformSignal
```
Returns a signal with the value that is the interpolation of the values of the given signals.

#
**mod**

```
mod(x: ScalarSignal, y: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the floating-pointRemainder of the division of the value of the first signal by the value of the second signal.
 
**See Also**: `ScalarSignal.mod`

#
**monitorMany**


```
monitorMany(signals: { [string]: ScalarSignal}): EventSource
monitorMany(signals: { [string]: ScalarSignal}, config: {fireOnInitialValue: ?boolean}): EventSource
```

Returns an `EventSource` that emits an event every time when any value of the input signals change. The event contains a JSON object with the old and new values in the format:
 
```
{ "oldValues": oldValues, "newValues": newValues }
```

where `oldValues` and `newValues` are the JSON objects where keys are the names of the signals and values are old or new values of that signals correspondingly.
 
> **Note**: By default, there is no event fired for the initial value of the signal.If `config.fireOnInitialValue` is set to `true` then an event for initial signal value is also emitted. `oldValues` is unset for this initial event.

**See Also**: `ReactiveModule.monitor`

#
**mul**

```
mul(x: ScalarSignal, y: ScalarSignal): ScalarSignal
mul(x: VectorSignal, y: ScalarSignal): VectorSignal
mul(x: ScalarSignal, y: VectorSignal): VectorSignal
mul(x: VectorSignal, y: VectorSignal): VectorSignal
```

Returns a signal with the value that is the product of the values of the given signals.
 
**See Also**: `ScalarSignal.mul`, `VectorSignal.mul`

#
**mulList**

```
mulList(x: Array<number>): ScalarSignal
```

Returns a signal with the value that is the product of the values in an array

#
**ne**

```
ne(lhs: ScalarSignal,Rhs: ScalarSignal): BoolSignal
ne(lhs: StringSignal,Rhs: StringSignal): BoolSignal
ne(lhs: BoolSignal,Rhs: BoolSignal): BoolSignal
```

Returns a Boolean signal that takes the value of `true` every time when the value of the left-hand-side signal is**not equal** to the value of theRight-hand-side one, and the value of `false` all other time.
 
> **Note**: the scalar values are tested for exact equality. For some applications it might beReasonable to perform a non-strict comparison allowing the values to be within a small distance one from another.

**See Also**: `ScalarSignal.ne`, `StringSignal.ne`, `BoolSignal.ne`

#
**neg**

```
neg(x: ScalarSignal): ScalarSignal
neg(x: VectorSignal): VectorSignal
```

Returns a signal with the negated value of the given signal.
 
**See Also**: `ScalarSignal.neg`, `VectorSignal.neg`

#
**normalize**

```
normalize(v: VectorSignal): VectorSignal
normalize(): VectorSignal
```

Returns the normalized (unit) vector in the direction of the original vector as a `VectorSignal`.

#
**not**

```
not(signal: BoolSignal): BoolSignal
```

Returns a signal with the logically negated value of the given signal.
 
**See Also**: `BoolSignal.not`

#
**once**

```
once(): EventSource
```

Returns an `EventSource` that emits exactly one empty event as soon as possible.

#
**or**

```
or(lhs: BoolSignal,Rhs: BoolSignal): BoolSignal
```

Returns a signal with the value that is the logical disjunction of the values of the given signals. It is `true` every time at least one of the input signals is `true` and `false` at all other times.
 
**See Also**: `BoolSignal.or`

#
**orList**

```
orList(x: Array<BoolSignal>): BoolSignal
```

Returns a signal with the value that is the logical or of the values in an array

#
**pack2**

```
pack2(x: ScalarSignal, y: ScalarSignal): Point2DSignal
pack2(x: ScalarSignal, y: Point2DSignal): PointSignal
pack2(x: Point2DSignal, y: ScalarSignal): PointSignal
pack2(x: ScalarSignal, y: PointSignal): Point4DSignal
pack2(x: PointSignal, y: ScalarSignal): Point4DSignal
pack2(x: Point2DSignal, y: Point2DSignal): Point4DSignal
```

Packs two Scalar or Point signals into a bigger Point signal.

#
**pack3**

```
pack3(x: ScalarSignal, y: ScalarSignal, z: ScalarSignal): PointSignal
pack3(x: ScalarSignal, y: ScalarSignal, z: Point2DSignal): Point4DSignal
pack3(x: ScalarSignal, y: Point2DSignal, z: ScalarSignal): Point4DSignal
pack3(x: Point2DSignal, y: ScalarSignal, z: ScalarSignal): Point4DSignal
```

Packs three Scalar or Point signals into a bigger Point signal.

#
**pack4**

```
pack4(x: ScalarSignal, y: ScalarSignal, z: ScalarSignal, w: ScalarSignal): Point4DSignal
```

Packs four `ScalarSignals` into a `Point4DSignal`.

#
**point**

```
point(x: ScalarSignal, y: ScalarSignal, z: ScalarSignal): PointSignal
```

Combines three signals andReturns theResult as a `PointSignal`.

#
**point2d**

```
point2d(x: ScalarSignal, y: ScalarSignal): PixelPointSignal
```

Combines two signals andReturns theResult as a `PixelPointSignal`.

#
**pow**

```
pow(base: ScalarSignal, exponent: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the base signalRaised to the power of the exponent signal.
 
TheResult is undefined if the base is negative, or if the base is zero and the exponent is not positive.
 
**See Also**: `ScalarSignal.pow`

#
**reflect**

```
reflect(incident: VectorSignal, normal: VectorSignal): VectorSignal
Reflect(normal: VectorSignal): VectorSignal
```

 Calculates theReflection direction for an incident vector and a normal as a `VectorSignal`.

#
**rotation**

```
rotation(w: number, x: number, y: number, z: number):Rotation
```

Creates 'Rotation' from quaternion components.

#
**round**

```
round(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is theRounded value of the given signal.
 
> **Note**: When the fractional part is 0.5, itRounds the number away from zero, which is at odds with JavaScript standard behavior ofRounding it always up in such cases. Therefore, this function is NOT exactly theReactive counterpart of the standard JavaScript `Math.round` utility.

**See Also**: `ScalarSignal.round`

#
**scale**

```
scale(x: ScalarSignal, y: ScalarSignal, z: ScalarSignal): ScaleSignal
```

Combines three signals andReturns theResult as a `ScaleSignal`.

#
**schmittTrigger**

```
schmittTrigger(signal: ScalarSignal, config: { low: number, high: number, initialValue: ?boolean}): BoolSignal
```

Returns a Boolean signal that is `true` when the input is strictly greater than the upper threshold, and `false` when it is strictly less than the lower threshold.
For input values between and including the thresholds, the Shmitt triggerReturns the same value as at the previous update, or**initialValue** if this is the first update.
 
> **Note**: The initialValue is assumed to be `false` if it isn't specified.

#
**sign**

```
sign(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the sign of the given signal. Possible sign values: NaN, -0.0, 0.0, -1.0, 1.0.
 
> **Note**: this function is theReactive counterpart of the standard JavaScript `Math.sign` utility.

**See Also**: `ScalarSignal.sign`

#
**sin**

```
sin(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the sine of the value of the given signal (interpreted asRadians).

#
**smoothStep**

```
smoothStep(x: ScalarSignal, edge0: ScalarSignal, edge1: ScalarSignal): ScalarSignal
```

Returns 0.0 if x is less than edge0, and 1.0 if x is greater than edge1.
If x is between edge0 and edge1, smooth Hermite interpolation is performed.

#
**sqrt**

```
sqrt(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the squareRoot of the value of the given signal.
 
**See Also**: `ScalarSignal.sqrt`

#
**step**

```
step(x: ScalarSignal, edge: ScalarSignal): ScalarSignal
```

Returns 0.0 if x is less than edge, and 1.0 isReturned otherwise.

#
**sub**

```
sub(x: ScalarSignal, y: ScalarSignal): ScalarSignal
sub(x: PointSignal, y: VectorSignal): PointSignal
sub(x: VectorSignal, y: VectorSignal): VectorSignal
sub(x: PointSignal, y: PointSignal): VectorSignal
```

Returns a signal with the value that is the difference of the values of the given signals.
 
**See Also**: `ScalarSignal.sub`, `VectorSignal.sub`, `PointSignal.sub`

#
**sum**

```
sum(x: ScalarSignal, y: ScalarSignal): ScalarSignal
sum(x: PointSignal, y: VectorSignal): PointSignal
sum(x: VectorSignal, y: PointSignal): PointSignal
sum(x: VectorSignal, y: VectorSignal): VectorSignal
```

Returns a signal with the value that is the sum of the values of the given signals.
 
> **Note**: `add` and `sum` functions are synonyms, the behavior they provide is equivalent.

**See Also**: `ReactiveModule.sum`, `ScalarSignal.add`, `PointSignal.add`, `VectorSignal.add`

#
**sumList**

```
sumList(x: Array<number>): ScalarSignal
```

Returns a signal with the value that is the sum of the values in an array

#
**tan**

```
tan(x: ScalarSignal): ScalarSignal
```

Returns a signal with the value that is the tangent of the value of the given signal (interpreted asRadians).

#
**toRange**

```
toRange(x: ScalarSignal, min: ScalarSignal, max: ScalarSignal): ScalarSignal
```

Maps x from [0.0, 1.0]Range to [min, max]Range.

#
**val**

```
val(constant: number): ScalarSignal
val(constant: string): StringSignal
val(constant: boolean): BoolSignal
```

Returns a signal that has a constant value which is specified by the argument.
 
> **Note**: Primitive types are implicitly converted to constant signals when passed as function or property-setter arguments, therefore using `val` in such scenarios is notRequired.

#
**vector**

```
vector(x: ScalarSignal, y: ScalarSignal, z: ScalarSignal): VectorSignal
```

Combines three signals andReturns theResult as a `VectorSignal`.

#
**xor**
```
xor(lhs: BoolSignal,Rhs: BoolSignal): BoolSignal
```

Returns a signal with the value that is the logical exclusive disjunction of the values of the given signals. It is `true` every time exactly one of the input signals is `true` and `false` at all other times.

> **Note**: It is equivalent to `ReactiveModule.ne`.

**See Also**: `BoolSignal.xor`

#
**xorList**
```
xorList(x: Array<BoolSignal>): BoolSignal
```

Returns a signal with the value that is the logical xor of the values in an array
