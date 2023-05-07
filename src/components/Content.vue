<template>
    <div class="osg-content osg-padding-8">
        <Title title="Roman Numeral Converter, Advanced version" />
        <RulesText />

        <div class="osg-grid">
            <div class="osg-grid__column--12 osg-grid__column--4-breakpoint-medium">
                <div class="osg-input osg-margin-top-8">
                    <label class="osg-input__label" id="roman-value-input">
                        Roman Numeral String
                        <input class="osg-input__input" v-model="romanNumeralValue" ref="romanNumeralValue" type="text" autocomplete="roman-numeral" placeholder="example: XVI" aria-describedby="roman-value-input">
                    </label>
                    <div class="osg-input__required">* Required</div>
                    <Error v-show="errorVisible" :error="error" />
                    <Result v-show="resultVisible" :result="result" />
                </div>
            </div>
        </div>
        <button type="submit" @click="convertRomanNumeral" class="osg-button osg-margin-top-4" aria-label="Convert Roman Numeral to number">Convert to number</button>   
    </div>
</template>

<script>
import Title from './Title.vue'
import RulesText from './RulesText.vue'
import Error from './Error.vue'
import Result from './Result.vue'

export default {
    name: 'Content',
    components: {
        Title,
        RulesText,
        Error,
        Result,
    
    },
    data() {
        return {
            romanNumeralValue: '',
            errorVisible: false,
            error: '',
            resultVisible: false,
            result: '',
        };
    },
    methods: {
        convertRomanNumeral() {
            this.errorVisible = false;
            this.resultVisible = false;

            const url = 'http://localhost:8000/api/roman-numerals-advanced';
            const data = {
                romanNumeralString: this.romanNumeralValue,
            };

            fetch(url, {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
                body: JSON.stringify(data)
            })
            .then(response => response.json())
            .then(json => {
                
                if(json.status == 'ok') {
                    this.resultVisible = true;
                    this.result = `Roman Numeral String ${json.payload.romanNumeral} is ${json.payload.result}`
                
                } else if(json.status == 'error') {
                    this.errorVisible = true;
                    this.error = json.payload;
                
                }

            })
            .catch(error => {
                //Handle error
            });
        }
    }
}
</script>